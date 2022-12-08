# Clima

### Graph

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/1034?u=d0doooh)

![](https://community-assets.home-assistant.io/optimized/4X/5/3/1/5319ee05d540645abfcf76f753260143ed0d3635_2_690x291.png)

**Entities to replace:**
* sensor.dummy_temperature_01 `Required`
* sensor.dummy_humidity_01 `Required`

```yaml
- type: custom:stack-in-card
    cards:
      - type: grid
        square: false
        columns: 2
        cards:
          - type: custom:mushroom-entity-card
            entity: sensor.dummy_temperature_01
            primary_info: state
            secondary_info: name
            name: Temperature
            icon_color: green
          - type: custom:mushroom-entity-card
            entity: sensor.dummy_humidity_01
            primary_info: state
            secondary_info: name
            name: Humidity
            icon_color: blue
      - type: custom:mini-graph-card
        entities:
          - entity: sensor.dummy_temperature_01
            name: Temperature
            color: '#00bb33'
          - entity: sensor.dummy_humidity_01
            name: Humidity
            color: '#2196f3'
            y_axis: secondary
        hours_to_show: 24
        line_width: 3
        font_size: 50
        animate: true
        show:
          name: false
          icon: false
          state: false
          legend: false
          fill: fade
```