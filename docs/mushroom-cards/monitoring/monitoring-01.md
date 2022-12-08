# Misc

### Reminder Card

Author: [Tim_Knowlden](https://community.home-assistant.io/u/Tim_Knowlden) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/2757?u=d0doooh)

![](https://community-assets.home-assistant.io/original/4X/1/1/5/1157d43ae34e7002154e78a2c08b7044669f12a4.png)

**Entities to replace:**
* dummy_date_01 `Required`
* dummy_date_02 `Required`

```yaml
type: custom:vertical-stack-in-card
cards:
  - type: custom:mushroom-title-card
    title: '{{ user }}, Here are you reminders!'
    subtitle: ''
  - type: custom:decluttering-card
    template: rec_event
    variables:
      - entity: input_datetime.dummy_date_01
      - name: Kitchen Sink Water Filter
      - icon: water-opacity
      - interval: 182
      - interval_text: (due every 6 Months)
  - type: custom:decluttering-card
    template: rec_event
    variables:
      - entity: input_datetime.dummy_date_02
      - name: Tim Toothbrush head replacement
      - icon: toothbrush
      - interval: 93
      - interval_text: (due every 3 Months)
 ```

Decluttering Card template:
 ```yaml
decluttering_templates:
  rec_event:
    default:
      - icon: calendar-clock
      - next_text: Next due in
      - overdue_text: Overdue by
      - almost_due_offset: 1
      - unit_sec: 86400
      - interval_text: ''
      - service: script.script_set_timedate
      - comments: Resets the timer of last event to now
    card:
      type: custom:mushroom-template-card
      entity: '[[entity]]'
      icon: mdi:[[icon]]
      icon_color: >-
        {%- set ts_period = [[interval]]*[[almost_due_offset]]*[[unit_sec]] %}

        {%- set ts_event = as_timestamp(states.[[entity]].state) %}

        {%- set ts_now = as_timestamp(now())|round(0) %}

        {%- set ts_delta = (ts_now - ts_event) %}

        {% if (ts_period != 0) and (ts_delta > ts_period) %}red {% elif
        (ts_period-ts_delta) < [[almost_due_offset]]*[[unit_sec]] %}orange {%
        endif %}
      primary: '[[name]]'
      layout: horizontal
      tap_action:
        action: call-service
        service: '[[service]]'
        service_data:
          entity: '[[entity]]'
          timedate: 0
        confirmation:
          text: Reset the timer of last event to now?
      secondary: >-
        {%- set ts_period = [[interval]]*[[unit_sec]] %} {%- set ts_event =
        as_timestamp(states.[[entity]].state) %} {%- set ts_now =
        as_timestamp(now())|round(0) %} {%- set ts_delta = (ts_now - ts_event)
        %} {%- set ts_xdiff = (ts_period - ts_delta)|abs %} {% if ts_delta <
        ts_period %}[[next_text]] {% else %}[[overdue_text]] {% endif %}{% if
        ts_xdiff >= 604800 %}{{ (ts_xdiff // 604800) | int }}w, {{ (ts_xdiff %
        604800 // 86400) | int }}d {% elif ts_xdiff >= 86400 %}{{ (ts_xdiff %
        604800 // 86400) | int }}d {% elif ts_xdiff >= 3600 %}{{ (ts_xdiff %
        86400 // 3600) | int }}h {% elif ts_xdiff >= 600 %}{{ (ts_xdiff % 3600
        // 60) | int }}m {% elif ts_xdiff >= 60 %}{{ (ts_xdiff % 3600 // 60) |
        int }}m, {{ (ts_xdiff % 60) | int }}s {% else %}{{ (ts_xdiff % 60) | int
        }}s {% endif %} [[interval_text]].
      style: |-
        {%- set ts_period = [[interval]]*86400 %}
        {%- set ts_event = as_timestamp(states.[[entity]].state) %}
        {%- set ts_now = as_timestamp(now())|round(0) %}
        {%- set ts_delta = (ts_now - ts_event) %}
        ha-card {
          border: solid 2px {% if (ts_period != 0) and (ts_delta > ts_period) %}red {% elif (ts_period-ts_delta) < [[almost_due_offset]]*[[unit_sec]] %}orange {% elif (ts_period == 0) or (ts_delta < ts_period) %}var(--card-background-color) {% else %}red {% endif %};
        }
 ```

 ```yaml
 alias: Set Timedate
sequence:
  - service: input_datetime.set_datetime
    data:
      timestamp: >-
        {{ now().timestamp() + (timedate | default(0)) * (unit | default(86400))
        }}
      entity_id: "{{ entity }}"
mode: single
 ```


### 3D Printer

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/1811?u=d0doooh)

![](https://community-assets.home-assistant.io/optimized/4X/0/5/2/05284fdf4df21735e0474a80265c7d05103226d7_2_269x500.png)

**Entities to replace:**
* switch.3d_printer_power `Required`
* camera.3d_printer_camera `Required`
* button.octoprint_pause_job `Required`
* button.octoprint_resume_job `Required`
* button.octoprint_stop_job `Required`
* http://octopi.local `Required` 
* sensor.octoprint_current_state `Required` 
* sensor.octoprint_estimated_finish_time `Required` 
* sensor.3d_printer_power_power `Required` 
* sensor.octoprint_job_percentage `Required` 
* sensor.octoprint_actual_bed_temp `Required` 
* sensor.octoprint_target_bed_temp `Required` 
* sensor.octoprint_actual_tool0_temp `Required` 
* sensor.octoprint_target_tool0_temp `Required` 

**Helpers to create:**
* input_boolean.3d_printer_dropdown `Required`

```yaml
type: custom:stack-in-card
cards:
  - type: custom:layout-card
    layout_type: custom:grid-layout
    layout:
      grid-template-columns: auto 33px
      margin: '-4px -4px -8px -4px'
    cards:
      - type: custom:mushroom-template-card
        primary: 3D Printer
        entity: switch.3d_printer_power
        secondary: '{{ states(entity) | title }}'
        icon: mdi:printer-3d
        icon_color: '{{ ''light-blue'' if is_state(entity, ''on'') else ''disabled'' }}'
        tap_action:
          action: toggle
        hold_action:
          action: none
        card_mod:
          style: |
            ha-card {
              background: none;
              --ha-card-box-shadow: 0px;
            }
      - type: custom:mushroom-template-card
        entity: input_boolean.3d_printer_dropdown
        primary: ''
        secondary: ''
        icon: >-
          {{ 'mdi:chevron-down' if is_state(entity, 'off') else 'mdi:chevron-up'
          }}
        icon_color: disabled
        hold_action:
          action: none
        card_mod:
          style: |
            ha-card {
              align-items: flex-end;
              background: none;
              --ha-card-box-shadow: 0px;
            }
            mushroom-shape-icon {
              --shape-color: none !important;
            }  
  - type: conditional
    conditions:
      - entity: input_boolean.3d_printer_dropdown
        state: 'on'
    card:
      type: custom:stack-in-card
      cards:
        - type: custom:layout-card
          cards:
            - type: picture-entity
              show_state: false
              show_name: false
              camera_view: auto
              entity: camera.3d_printer_camera
        - type: custom:stack-in-card
          mode: horizontal
          keep:
            background: true
            border_radius: true
            margin: true
          cards:
            - type: custom:mushroom-template-card
              entity: button.octoprint_pause_job
              icon: mdi:pause
              icon_color: orange
              layout: vertical
              tap_action:
                action: toggle
              card_mod:
                style: |
                  ha-card { 
                    background: rgba(var(--rgb-orange), 0.1);
                    width: 66px;
                    border-radius: 50%;
                    margin-left: auto;
                    margin-right: auto;
                  }
            - type: custom:mushroom-template-card
              entity: button.octoprint_resume_job
              icon: mdi:play
              icon_color: green
              layout: vertical
              tap_action:
                action: toggle
              card_mod:
                style: |
                  ha-card { 
                    background: rgba(var(--rgb-green), 0.1);
                    width: 66px;
                    border-radius: 50%;
                    margin-left: auto;
                    margin-right: auto;
                  }
            - type: custom:mushroom-template-card
              entity: button.octoprint_stop_job
              icon: mdi:stop
              icon_color: red
              layout: vertical
              tap_action:
                action: toggle
              card_mod:
                style: |
                  ha-card { 
                    background: rgba(var(--rgb-red), 0.1);
                    width: 66px;
                    border-radius: 50%;
                    margin-left: auto;
                    margin-right: auto;
                  }
          card_mod:
            style: |
              ha-card {
                #background: none;
                --ha-card-box-shadow: 0px;
              }
        - type: custom:layout-card
          layout_type: custom:grid-layout
          layout:
            grid-template-columns: 197px auto
            margin: '-4px -4px -8px -4px'
          cards:
            - type: custom:stack-in-card
              cards:
                - type: custom:mushroom-entity-card
                  entity: sensor.octoprint_current_state
                  icon_color: green
                  tap_action:
                    action: url
                    url_path: http://octopi.local
                  icon: si:octopusdeploy
                  card_mod:
                    style: |
                      ha-card {
                        --badge-size: 0px !important;
                      }
                  primary_info: name
                  secondary_info: state
                  name: OctoPrint Status
                - type: custom:mushroom-entity-card
                  entity: sensor.octoprint_estimated_finish_time
                  icon_color: light-blue
                  tap_action:
                    action: none
                  primary_info: name
                  secondary_info: state
                  name: Est. Finish Time
                - type: custom:mushroom-template-card
                  entity: sensor.3d_printer_power_power
                  icon_color: '{{ ''amber'' if states(entity) | int > 0 else ''disabled'' }}'
                  tap_action:
                    action: none
                  primary: Power Use
                  secondary: '{{ states(entity) }} W'
                  icon: mdi:flash
              card_mod:
                style: |
                  ha-card {
                    margin-top: 6px;
                    background: none;
                    --ha-card-box-shadow: 0px;
                  }
            - type: custom:stack-in-card
              cards:
                - type: custom:apexcharts-card
                  header:
                    show: false
                  series:
                    - entity: sensor.octoprint_job_percentage
                      name: Job Progress
                      color: rgb(3, 169, 244)
                      show:
                        legend_value: false
                  chart_type: radialBar
                  apex_config:
                    legend:
                      show: false
                    chart:
                      height: 230px
                    plotOptions:
                      radialBar:
                        hollow:
                          size: 80%
                        dataLabels:
                          name:
                            show: false
                          value:
                            show: false
                        track:
                          strokeWidth: 80%
                          margin: 0
                    fill:
                      type: gradient
                      gradient:
                        shade: light
                        type: horizontal
                        shadeIntensity: 0.3
                        inverseColors: false
                        opacityFrom: 1
                        opacityTo: 1
                        stops:
                          - 0
                          - 50
                          - 55
                          - 90
                - type: custom:mushroom-entity-card
                  entity: sensor.octoprint_job_percentage
                  primary_info: state
                  secondary_info: name
                  name: Job Progress
                  icon_color: light-blue
                  layout: vertical
                  card_mod:
                    style: |
                      ha-card {
                        margin-top: -165px;
                        width: 140px;
                        margin-left: auto;
                        margin-right: auto;
                      }
              card_mod:
                style: |
                  ha-card {
                    background: none;
                    --ha-card-box-shadow: 0px;
                  }
        - type: custom:stack-in-card
          cards:
            - type: grid
              square: false
              columns: 2
              cards:
                - type: custom:stack-in-card
                  cards:
                    - type: custom:apexcharts-card
                      chart_type: radialBar
                      series:
                        - entity: sensor.octoprint_actual_bed_temp
                          color: rgb(103, 58, 183)
                          max: 110
                          show:
                            legend_value: false
                        - entity: sensor.octoprint_target_bed_temp
                          color: rgb(103, 58, 183)
                          max: 110
                          show:
                            legend_value: false
                      apex_config:
                        plotOptions:
                          radialBar:
                            offsetY: -15
                            startAngle: -105
                            endAngle: 105
                            hollow:
                              size: 60%
                            dataLabels:
                              name:
                                show: false
                              value:
                                show: false
                        legend:
                          show: false
                        chart:
                          height: 220px
                        fill:
                          type: gradient
                          gradient:
                            shade: light
                            type: horizontal
                            shadeIntensity: 0.3
                            inverseColors: false
                            opacityFrom: 1
                            opacityTo: 1
                            stops:
                              - 0
                              - 50
                              - 55
                              - 90
                    - type: custom:mushroom-template-card
                      primary: Bed Temp
                      secondary: >-
                        {{ states(entity) | round(1) }} °C / {{
                        states('sensor.octoprint_target_bed_temp') | round (1)
                        }} °C
                      icon: mdi:thermometer-lines
                      entity: sensor.octoprint_actual_bed_temp
                      icon_color: deep-purple
                      layout: vertical
                      card_mod:
                        style: |
                          ha-card {
                            margin-top: -80px;
                            width: 175px;
                            margin-left: auto;
                            margin-right: auto;
                          }
                - type: custom:stack-in-card
                  cards:
                    - type: custom:apexcharts-card
                      chart_type: radialBar
                      series:
                        - entity: sensor.octoprint_actual_tool0_temp
                          color: rgb(233, 30, 99)
                          max: 240
                          show:
                            legend_value: false
                        - entity: sensor.octoprint_target_tool0_temp
                          color: rgb(233, 30, 99)
                          max: 240
                          show:
                            legend_value: false
                      apex_config:
                        plotOptions:
                          radialBar:
                            offsetY: -15
                            startAngle: -105
                            endAngle: 105
                            hollow:
                              size: 60%
                            dataLabels:
                              name:
                                show: false
                              value:
                                show: false
                        legend:
                          show: false
                        chart:
                          height: 220px
                          stack: true
                        fill:
                          type: gradient
                          gradient:
                            shade: light
                            type: horizontal
                            shadeIntensity: 0.3
                            inverseColors: false
                            opacityFrom: 1
                            opacityTo: 1
                            stops:
                              - 0
                              - 50
                              - 55
                              - 90
                    - type: custom:mushroom-template-card
                      primary: Tool Temp
                      secondary: >-
                        {{ states(entity) | round(1) }} °C / {{
                        states('sensor.octoprint_target_tool0_temp') | round (1)
                        }} °C
                      icon: mdi:printer-3d-nozzle
                      entity: sensor.octoprint_actual_tool0_temp
                      icon_color: pink
                      layout: vertical
                      card_mod:
                        style: |
                          ha-card {
                            margin-top: -80px;
                            width: 175px;
                            margin-left: auto;
                            margin-right: auto;
                          }
          card_mod:
            style: |
              ha-card {
                background: none;
                --ha-card-box-shadow: 0px;
              }
```