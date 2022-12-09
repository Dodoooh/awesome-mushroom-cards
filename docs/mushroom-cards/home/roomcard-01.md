# Room cards:

### Interactive Room Card

Author: [theandouz](https://community.home-assistant.io/u/theandouz) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3740?u=d0doooh)

![](https://community-assets.home-assistant.io/original/4X/9/0/b/90b498143a48528b1bcd080e7c2cc1c243307706.gif)

**Entities to replace:**
* media_player.media_player_01 `Required`
* lock.dummy_lock_01 `Required`
* light.dummy_light_01 `Required`
* light.dummy_light_02 `Required`
* light.dummy_light_03 `Required`
* light.dummy_light_04 `Required`
* sensor.temp_01 `Required`
* binary_sensor.dummy_alarm `Required`
* sensor.ps5_activity `Required`

```yaml
type: custom:vertical-stack-in-card
cards:
  - type: custom:swipe-card
    parameters:
      spaceBetween: 8
    cards:
      - type: custom:mushroom-template-card
        primary: Family Room
        secondary: '{{ states(''sensor.temp_01'') }} °F'
        icon: mdi:coffee
        layout: horizontal
        entity: light.dummy_light_01
        tap_action:
          action: navigate
          navigation_path: family_room
        hold_action:
          action: none
        double_tap_action:
          action: toggle
        picture: >-
          {% if is_state('media_player.media_player_01','playing') %}
            {{ states.media_player.media_player_01.attributes.entity_picture }}
          {% else %} {% endif %}
        card_mod:
          style:
            mushroom-shape-avatar$: |
              .picture {
                {% if is_state('media_player.media_player_01','playing') %}
                  animation: rotation 4s linear infinite;
                {% else %}  {% endif %}
              }
              @keyframes rotation {
                100% {
                  transform: rotate(360deg);
                }
              }
            mushroom-shape-icon$: |
              .shape {
                {% set r = state_attr(config.entity, 'rgb_color')[0] %}
                {% set g = state_attr(config.entity, 'rgb_color')[1] %}
                {% set b = state_attr(config.entity, 'rgb_color')[2] %}
              {% if is_state(config.entity, 'on') %}
                --icon-color: rgb( {{r}}, {{g}}, {{b}} ) !important;
                --shape-color: rgba( {{r}}, {{g}}, {{b}}, 0.2 ) !important;
              {% endif %}
              }
            .: |
              ha-card {
                border-radius: 16px 16px 0px 0px;
              }
      - type: custom:mushroom-media-player-card
        entity: media_player.media_player_01
        use_media_artwork: true
        use_media_info: true
        collapsible_controls: true
        show_volume_level: false
        fill_container: false
        tap_action:
          action: call-service
          service: media_player.media_play_pause
          data: {}
          target:
            entity_id: media_player.media_player_01
        card_mod:
          style: |
            ha-card {
              border-radius: 16px 16px 0px 0px;
              {% if is_state(config.entity, 'playing') or is_state(config.entity, 'paused') %}
                background: rgba(var(--rgb-card-background-color), 0.9) url( '{{ state_attr(config.entity, "entity_picture" ) }}' ) center no-repeat;
                background-size: cover;
                background-blend-mode: overlay;
              {% else %}
              {% endif %}  
            }
      - type: conditional
        conditions:
          - entity: sensor.ps5_activity
            state: playing
        card:
          type: custom:button-card
          styles:
            card:
              - width: 242px
              - height: 66px
          card_mod:
            style: |
              ha-card {
                border-radius: 18px 18px 0px 0px;
                background-image: url( '{{ state_attr( "sensor.ps5_activity", "title_image" ) }}' );
                background-position: center;
                background-repeat: no-repeat;
                background-size: cover;
                position: relative;
                background-blend-mode: overlay;
                background-color: rgba(25,25,25,0.3); 
              }
      - type: custom:stack-in-card
        mode: horizontal
        keep:
          background: true
        cards:
          - type: custom:mushroom-template-card
            primary: ''
            secondary: ''
            layout: vertical
            icon: |-
              {% if is_state(config.entity, "locked") %}
                mdi:lock
              {% else %}
                mdi:lock-open
              {% endif%}
            entity: lock.dummy_lock_01
            icon_color: |-
              {% if is_state(config.entity, "locked") %}
                green
              {% else %}
                red
              {% endif%}
            tap_action:
              action: toggle
            card_mod:
              style: |
                ha-card {
                  {% if is_state(config.entity,'locked') %}
                      background: rgba(var(--rgb-light-green),0.2);
                  {% else %}
                      background: rgba(var(--rgb-light-red),0.2);
                  {% endif %}
                }
          - type: custom:mushroom-light-card
            entity: light.dummy_light_02
            layout: vertical
            primary_info: none
            secondary_info: none
            card_mod:
              style: |
                ha-card {
                  {% if is_state(config.entity, 'on') %}
                     background: rgba(var(--rgb-light-amber),0.1);
                  {% else %}
                     background: transparent;
                  {% endif %}
                }
        card_mod:
          style: |
            ha-card {
              border-radius: 16px 16px 0px 0px;
            } 
  - type: custom:mushroom-chips-card
    card_mod:
      style: |
        ha-card {
          --ha-card-box-shadow: none;
          --chip-background: none;
          --chip-spacing: 0;
        }
    alignment: end
    chips:
      - type: conditional
        conditions:
          - entity: light.dummy_light_03
            state: 'on'
        chip:
          type: template
          icon_color: |-
            {% set state=states(entity) %}
            {% if state=='on' %}
               pink
            {%else%}
              grey
            {%endif%}
          entity: light.dummy_light_03
          icon: mdi:bird
          tap_action:
            action: toggle
      - type: conditional
        conditions:
          - entity: light.dummy_light_04
            state: 'on'
        chip:
          type: light
          entity: light.dummy_light_04
          content_info: none
          use_light_color: true
          icon: mdi:lamp
      - type: conditional
        conditions:
          - entity: lock.dummy_lock_01
            state: unlocked
        chip:
          type: template
          icon_color: red
          icon: mdi:lock-open
          tap_action:
            action: call-service
            service: lock.lock
            data: {}
            target:
              entity_id: lock.dummy_lock_01
      - type: conditional
        conditions:
          - entity: binary_sensor.dummy_alarm
            state: 'on'
        chip:
          type: template
          icon_color: red
          icon: mdi:door-open
card_mod:
  style: |
    ha-card {
      height: 102px;
      {% if is_state('light.dummy_light_01', 'on') %}
          background: rgba({{ state_attr('light.dummy_light_01','rgb_color') [0] }},
                  {{ state_attr('light.dummy_light_01','rgb_color') [1] }},
                  {{ state_attr('light.dummy_light_01','rgb_color') [2] }},0.1);
      {% endif %}
      }
```


### Room Card 01

Author: [Boostin4HP](https://community.home-assistant.io/u/Boostin4HP) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3222?u=d0doooh)

![](https://community-assets.home-assistant.io/optimized/4X/b/3/9/b396dc023bb3977847c9ba84508c57fc032a5c81_2_690x468.jpeg)

**Entities to replace:**
* sensor.dummy_battery_level_01 `Required`
* light.dummy_light_01 `Required`
* lock.dummy_lock_01 `Required`
* binary_sensor.dummy_window `Required`

```yaml
type: custom:stack-in-card
cards:
  - type: custom:stack-in-card
    mode: horizontal
    cards:
      - type: custom:mushroom-template-card
        primary: null
        secondary: null
        icon: mdi:door
        fill_container: true
        layout: horizontal
        multiline_secondary: false
        badge_icon: |-
          {% set bl = states('sensor.dummy_battery_level_01') | int %}
          {% if bl < 10 %} mdi:battery-outline
          {% elif bl < 20 %} mdi:battery-10
          {% elif bl < 30 %} mdi:battery-20
          {% elif bl < 40 %} mdi:battery-30
          {% elif bl < 50 %} mdi:battery-40
          {% elif bl < 60 %} mdi:battery-50
          {% elif bl < 70 %} mdi:battery-60
          {% elif bl < 80 %} mdi:battery-70
          {% elif bl < 90 %} mdi:battery-80
          {% elif bl < 100 %} mdi:battery-90
          {% elif bl == 100 %} mdi:battery
          {% else %} mdi:battery-unknown
          {% endif %}
        badge_color: |-
          {% set bl = states('sensor.dummy_battery_level_01') | int %}
          {% if bl < 10 %} red
          {% elif bl < 20 %} red
          {% elif bl < 30 %} red
          {% elif bl < 40 %} orange
          {% elif bl < 50 %} orange
          {% elif bl < 60 %} green
          {% elif bl < 70 %} green
          {% elif bl < 80 %} green
          {% elif bl < 90 %} green
          {% elif bl < 100 %} green
          {% elif bl == 100 %} green
          {% else %} disabled
          {% endif %}
        tap_action:
          action: navigate
          navigation_path: foyer
        icon_color: deep-purple
        hold_action:
          action: none
        double_tap_action:
          action: none
        card_mod:
          style: |
            :host {
              background: #1f1f1f;
              --mush-icon-size: 74px;
              height: 66px;
              margin-left: -26px !important;
            }
            mushroom-badge-icon {
              left: 178px;
              top: 17px;
            }
      - type: vertical-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Foyer
            secondary: null
            icon: null
            fill_container: true
            layout: horizontal
            multiline_secondary: false
            tap_action:
              action: navigate
              navigation_path: foyer
            icon_color: deep-purple
            hold_action:
              action: none
            double_tap_action:
              action: none
            card_mod:
              style: |
                :host {
                  background: #1f1f1f;
                  margin-top: 0px !important;
                  margin-left: -20px !important;
                  margin-bottom: -18px !important;
                }
          - type: custom:mushroom-light-card
            entity: light.dummy_light_01
            fill_container: true
            show_brightness_control: true
            icon_type: none
            primary_info: none
            secondary_info: none
            use_light_color: true
            layout: horizontal
            card_mod:
              style: |
                :host {
                  background: #1f1f1f;
                  margin-left: -22px !important;
                  margin-bottom: -18px !important;
                }
                ha-card {
                  --icon-size: 0px;
                  --control-height: 16px;
                  --control-top: 16px;
                  --control-border-radius: 5px;
                }
  - type: custom:mushroom-chips-card
    chips:
      - type: conditional
        conditions:
          - entity: light.dummy_light_01
            state: 'on'
        chip:
          type: entity
          entity: light.dummy_light_01
          icon_color: amber
          tap_action:
            action: call-service
            service: light.turn_off
            service_data: {}
            target:
              entity_id: light.dummy_light_01
          content_info: none
          icon: mdi:lightbulb
      - type: template
        entity: lock.dummy_lock_01
        icon: |-
          {% set state=states(entity) %}
          {% if state=='locked' %}
          mdi:lock
          {% elif state=='unlocked' %}
          mdi:lock-open-variant
          {% else %}
          grey
          {% endif %}
        tap_action:
          action: more-info
        icon_color: |-
          {% set state=states(entity) %}
          {% if state=='locked' %}
          disabled
          {% elif state=='unlocked' %}
          red
          {% else %}
          amber
          {% endif %}
      - type: template
        entity: binary_sensor.dummy_window
        icon: |-
          {% set state=states(entity) %}
          {% if state=='on' %}
          mdi:door-open
          {% elif state=='off' %}
          mdi:door-closed
          {% else %}
          mdi:door
          {% endif %}
        tap_action:
          action: more-info
        icon_color: |-
          {% set state=states(entity) %}
          {% if state=='on' %}
          red
          {% elif state=='off' %}
          disabled
          {% else %}
          amber
          {% endif %}
    alignment: end
    card_mod:
      style: |
        ha-card {
          --chip-box-shadow: none;
          --chip-background: none;
          --chip-spacing: 0;
          margin-right: 6px;
          margin-top: -5px
        }
card_mod:
  style: |
    ha-card {
      height: 100px;
      background: #1a1a1a;
      {% if is_state('light.dummy_light_01', 'on') %}
         background: rgba(255, 152, 0, 0.1);
      {% endif %}
    }
```