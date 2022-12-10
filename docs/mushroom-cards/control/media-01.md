# Media 01

## Cards:<!-- {docsify-ignore} -->

### Blurred Album Art Tablet Mode

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/4304?u=d0doooh)

![](https://community-assets.home-assistant.io/original/4X/3/c/d/3cd6f5ab1b7bc51f21e3f26126b36595c6f47d1f.gif)

**Entities to replace:**
* media_player.media_player_01 `Required`

```yaml
ttype: custom:stack-in-card
cards:
  - type: custom:mushroom-media-player-card
    entity: media_player.media_player_01
    icon: mdi:play
    use_media_info: true
    use_media_artwork: false
    show_volume_level: false
    media_controls:
      - play_pause_stop
      - previous
      - next
    volume_controls:
      - volume_buttons
      - volume_set
    fill_container: false
    card_mod:
      style: |
        mushroom-shape-icon {
          display: flex;
          <div data-gb-custom-block data-tag="set" data-0='media_content_type' data-1='media_content_type'></div>

          

<div data-gb-custom-block data-tag="if" data-0='tvshow' data-1='tvshow'></div>

            --card-mod-icon: mdi:television-classic;
            animation: flicker 1s linear infinite alternate;
          

<div data-gb-custom-block data-tag="elif" data-0='movie' data-1='movie'></div>

            --card-mod-icon: mdi:movie-roll;
            animation: spin 2s linear infinite reverse;
          

<div data-gb-custom-block data-tag="elif" data-0='music' data-1='music'></div>

            --card-mod-icon: mdi:music;
            animation: beat 1.3s ease-out infinite both;
          

<div data-gb-custom-block data-tag="elif" data-0='playlist' data-1='playlist'></div>

            --card-mod-icon: mdi:music;
            animation: beat 1.3s ease-out infinite both;
          

<div data-gb-custom-block data-tag="else">

            --card-mod-icon: mdi:play;
          

</div>

        }
        @keyframes flicker {
          0%, 31.98%, 32.98%, 34.98%, 36.98%, 39.98%, 67.98%, 68.98%, 95.98%, 96.98%, 97.98%, 98.98%, 100% { --icon-color: rgba(var(--rgb-indigo), 1); }
          32%, 33%, 35%, 36%, 37%, 40%, 68%, 69%, 96%, 97%, 98%, 99% { --icon-color: rgba(var(--rgb-indigo), 0.6); }
        }
        @keyframes beat {
          0%, 60% { --icon-symbol-size: 21px; }
          5%, 17%, 57% { --icon-symbol-size: 22px; }
          10%, 20%, 51% { --icon-symbol-size: 23px; }
          25%, 45% { --icon-symbol-size: 24px; }
          30%, 39% { --icon-symbol-size: 25px; }
          33% { --icon-symbol-size: 26px; }
        }
        ha-card {
          --ha-card-border-width: 0;
        }
        ha-card:before {
          content: "";
          background: url( '{{ state_attr("media_player.media_player_01", "entity_picture") }}' );
          background-size: contain;
          background-position: center;
          background-repeat: no-repeat;
          margin: 4px 4px 16px;
          filter: drop-shadow(0.35rem 0.35rem 0.4rem rgba(0, 0, 0, 0.5));
          filter: drop-shadow(4px 4px 6px rgba(0, 0, 0, 0.5));

          

<div data-gb-custom-block data-tag="set" data-0='media_content_type' data-1='media_content_type'></div>

          

<div data-gb-custom-block data-tag="if" data-0='tvshow' data-1='tvshow'></div>

            aspect-ratio: 16 / 9;
          

<div data-gb-custom-block data-tag="elif" data-0='movie' data-1='movie'></div>

            aspect-ratio: 2 / 3;
          

<div data-gb-custom-block data-tag="else">

            aspect-ratio: 1 / 1;
          

</div>

        }
  - type: conditional
    conditions:
      - entity: media_player.media_player_01
        state_not: 'off'
      - entity: media_player.media_player_01
        state_not: idle
    card:
      entity: media_player.media_player_01
      hide:
        icon: true
        name: true
        runtime: true
        source: true
        power: true
        state_label: true
        volume: true
        info: true
        progress: false
        controls: true
      more_info: false
      type: custom:mini-media-player
      toggle_power: false
      group: true
      card_mod:
        style:
          mmp-progress$: |
            paper-progress {
              {{ '--paper-progress-container-color: rgba(var(--rgb-indigo-color), 0.2) !important;' if is_state(config.entity, 'playing') }}
            }
          .: |
            ha-card {
              margin: 0px 12px 12px;
              --mmp-progress-height: 12px !important;
              height: var(--mmp-progress-height);
              --mmp-accent-color: rgb(var(--rgb-indigo-color));
              --mmp-border-radius: 12px !important;
              --ha-card-border-width: 0;
            }
card_mod:
  style: |
    ha-card:before {
      transform: translate3d(0,0,0);
      -webkit-transform: translate3d(0,0,0);
      

<div data-gb-custom-block data-tag="if" data-0='media_player.media_player_01' data-1='1' data-2='1' data-3='1' data-4='1' data-5='1' data-6='1' data-7=', '>

        content: "";
        position: absolute;
        height: 100%;
        width: 100%;
        background: url( '{{ state_attr('media_player.media_player_01', "entity_picture") }}' ) center no-repeat;
        filter: blur(150px) saturate(300%);
        background-size: cover;
        background-position: center;
      

</div> 
    }
```

### Blended Blurred Album Art

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/4232?u=d0doooh)

![Gif Animation 01](https://community-assets.home-assistant.io/original/4X/4/f/0/4f055ee2ee6d033b70bbd288206883b844732234.gif)

**Entities to replace:**
* media_player.media_player_01 `Required`

```yaml
type: custom:stack-in-card
cards:
  - type: custom:mushroom-media-player-card
    entity: media_player.media_player_01
    icon: mdi:play
    use_media_info: true
    use_media_artwork: false
    show_volume_level: false
    media_controls:
      - play_pause_stop
      - previous
      - next
    volume_controls:
      - volume_buttons
      - volume_set
    fill_container: false
    card_mod:
      style: |
        mushroom-shape-icon {
          display: flex;
          {% set media_type = state_attr(config.entity, 'media_content_type') %}
          {% if media_type == 'tvshow' %}
            --card-mod-icon: mdi:television-classic;
            animation: flicker 1s linear infinite alternate;
          {% elif media_type == 'movie' %}
            --card-mod-icon: mdi:movie-roll;
            animation: spin 2s linear infinite reverse;
          {% elif media_type == 'music' %}
            --card-mod-icon: mdi:music;
            animation: beat 1.3s ease-out infinite both;
          {% elif media_type == 'playlist' %}
            --card-mod-icon: mdi:music;
            animation: beat 1.3s ease-out infinite both;
          {% else %}
            --card-mod-icon: mdi:play;
          {% endif %}
        }
        @keyframes flicker {
          0%, 31.98%, 32.98%, 34.98%, 36.98%, 39.98%, 67.98%, 68.98%, 95.98%, 96.98%, 97.98%, 98.98%, 100% { --icon-color: rgba(var(--rgb-indigo), 1); }
          32%, 33%, 35%, 36%, 37%, 40%, 68%, 69%, 96%, 97%, 98%, 99% { --icon-color: rgba(var(--rgb-indigo), 0.6); }
        }
        @keyframes beat {
          0%, 60% { --icon-symbol-size: 21px; }
          5%, 17%, 57% { --icon-symbol-size: 22px; }
          10%, 20%, 51% { --icon-symbol-size: 23px; }
          25%, 45% { --icon-symbol-size: 24px; }
          30%, 39% { --icon-symbol-size: 25px; }
          33% { --icon-symbol-size: 26px; }
        }
        ha-card {
          --ha-card-border-width: 0;
        }
  - type: conditional
    conditions:
      - entity: media_player.media_player_01
        state_not: 'off'
      - entity: media_player.media_player_01
        state_not: idle
    card:
      entity: media_player.media_player_01
      hide:
        icon: true
        name: true
        runtime: true
        source: true
        power: true
        state_label: true
        volume: true
        info: true
        progress: false
        controls: true
      more_info: false
      type: custom:mini-media-player
      toggle_power: false
      group: true
      card_mod:
        style:
          mmp-progress$: |
            paper-progress {
              {{ '--paper-progress-container-color: rgba(var(--rgb-indigo-color), 0.2) !important;' if is_state(config.entity, 'playing') }}
            }
          .: |
            ha-card {
              margin: 0px 12px 12px;
              --mmp-progress-height: 12px !important;
              height: var(--mmp-progress-height);
              --mmp-accent-color: rgb(var(--rgb-indigo-color));
              --mmp-border-radius: 12px !important;
              --ha-card-border-width: 0;
            }
card_mod:
  style: |
    ha-card:before {
      content: "";
      position: absolute;
      height: 100%;
      width: 100%;
      {% if not is_state('media_player.media_player_01', 'idle') %}
        background: url( '{{ state_attr('media_player.media_player_01', "entity_picture") }}' ) center no-repeat;
      {% endif %} 
      filter: blur(150px) saturate(400%);
      background-size: cover;
    }
    ha-card {
      {% if not is_state('media_player.media_player_01', 'idle') %}
        background: url( '{{ state_attr("media_player.media_player_01", "entity_picture") }}' ), linear-gradient(to left, transparent, rgb(var(--rgb-card-background-color)) 50%);

        {% if state_attr('media_player.media_player_01', 'media_content_type') == 'tvshow' %}
          background-size: auto 100%, cover;
        {% else %}
          background-size: 50% auto, cover;
        {% endif %}

        background-position: right;
        background-repeat: no-repeat;
        background-blend-mode: saturation;
      {% endif %}
    }
```


### Ultrablur

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/4219?u=d0dooohh)

![Gif Animation 01](https://community-assets.home-assistant.io/original/4X/3/c/d/3cd6f5ab1b7bc51f21e3f26126b36595c6f47d1f.gif)


**Entities to replace:**
* media_player.media_player_01 `Required`

```yaml
type: custom:stack-in-card
cards:
  - type: custom:mushroom-media-player-card
    entity: media_player.media_player_01
    icon: mdi:play
    use_media_info: true
    use_media_artwork: false
    show_volume_level: false
    media_controls:
      - play_pause_stop
      - previous
      - next
    volume_controls:
      - volume_buttons
      - volume_set
    fill_container: false
    card_mod:
      style: |
        mushroom-shape-icon {
          display: flex;
          {% set media_type = state_attr(config.entity, 'media_content_type') %}
          {% if media_type == 'tvshow' %}
            --card-mod-icon: mdi:television-classic;
            animation: flicker 1s linear infinite alternate;
          {% elif media_type == 'movie' %}
            --card-mod-icon: mdi:movie-roll;
            animation: spin 2s linear infinite reverse;
          {% elif media_type == 'music' %}
            --card-mod-icon: mdi:music;
            animation: beat 1.3s ease-out infinite both;
          {% elif media_type == 'playlist' %}
            --card-mod-icon: mdi:music;
            animation: beat 1.3s ease-out infinite both;
          {% else %}
            --card-mod-icon: mdi:play;
          {% endif %}
        }
        @keyframes flicker {
          0%, 31.98%, 32.98%, 34.98%, 36.98%, 39.98%, 67.98%, 68.98%, 95.98%, 96.98%, 97.98%, 98.98%, 100% { --icon-color: rgba(var(--rgb-indigo), 1); }
          32%, 33%, 35%, 36%, 37%, 40%, 68%, 69%, 96%, 97%, 98%, 99% { --icon-color: rgba(var(--rgb-indigo), 0.6); }
        }
        @keyframes beat {
          0%, 60% { --icon-symbol-size: 21px; }
          5%, 17%, 57% { --icon-symbol-size: 22px; }
          10%, 20%, 51% { --icon-symbol-size: 23px; }
          25%, 45% { --icon-symbol-size: 24px; }
          30%, 39% { --icon-symbol-size: 25px; }
          33% { --icon-symbol-size: 26px; }
        }
        ha-card {
          --ha-card-border-width: 0;
        }
  - type: conditional
    conditions:
      - entity: media_player.media_player_01
        state_not: 'off'
      - entity: media_player.media_player_01
        state_not: idle
    card:
      entity: media_player.media_player_01
      hide:
        icon: true
        name: true
        runtime: true
        source: true
        power: true
        state_label: true
        volume: true
        info: true
        progress: false
        controls: true
      more_info: false
      type: custom:mini-media-player
      toggle_power: false
      group: true
      card_mod:
        style:
          mmp-progress$: |
            paper-progress {
              {{ '--paper-progress-container-color: rgba(var(--rgb-indigo-color), 0.2) !important;' if is_state(config.entity, 'playing') }}
            }
          .: |
            ha-card {
              margin: 0px 12px 12px;
              --mmp-progress-height: 12px !important;
              height: var(--mmp-progress-height);
              --mmp-accent-color: rgb(var(--rgb-indigo-color));
              --mmp-border-radius: 12px !important;
              --ha-card-border-width: 0;
            }
card_mod:
  style: |
    ha-card:before {
      content: "";
      position: absolute;
      height: 100%;
      width: 100%;
      {% if not is_state('media_player.media_player_01', 'idle') %}
        background: url( '{{ state_attr('media_player.media_player_01', "entity_picture") }}' ) center no-repeat;
      {% endif %} 
      filter: blur(150px) saturate(400%);
      background-size: cover;
    }
```


### Volume Slider

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/2142)

![Volume Slider](https://community-assets.home-assistant.io/optimized/4X/0/d/7/0d7a24009e0ea15f1324a0b292aee020839d55a9_2_517x150.png)


**Entities to replace:**
* input_number.dummy_volume `Required`

```yaml
type: custom:stack-in-card
cards:
  - type: custom:mushroom-template-card
    entity: input_number.dummy_volume
    icon: |
      {% set vol_level = states(entity) | float %}
      {% if vol_level == 0 %}
        mdi:volume-mute
      {% elif vol_level > 0.66 %}
        mdi:volume-high
      {% elif vol_level < 0.33 %}
        mdi:volume-low
      {% else %}
        mdi:volume-medium
      {% endif %}
    icon_color: indigo
    primary: Volume
    secondary: |
      {% set vol = states(entity) | float * 100 %}
      {{ vol | round | int }}%
  - type: custom:my-slider
    entity: input_number.dummy_volume
    radius: 12px
    height: 42px
    mainSliderColor: rgb(var(--mush-rgb-indigo))
    secondarySliderColor: rgba(var(--mush-rgb-indigo), 0.2)
    mainSliderColorOff: rgb(var(--mush-rgb-disabled))
    secondarySliderColorOff: rgba(var(--mush-rgb-disabled), 0.2)
    thumbHorizontalPadding: 0px
    thumbVerticalPadding: 0px
    thumbWidth: 0px
    card_mod:
      style: |
        ha-card {
          padding: 0px 11px 11px;
          --mush-rgb-disabled: 189,189,189;
          --mush-rgb-indigo: 63, 81, 181;
        }
```