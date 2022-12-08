# Dashboard cards:

### Energy Consumption

Author: [Boostin4HP](https://community.home-assistant.io/u/Boostin4HP) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3004?u=d0doooh)

![](https://community-assets.home-assistant.io/optimized/4X/5/c/2/5c2b86beeb3b0a105a8ce0f5d77ab1bd36798b77_2_690x432.jpeg)

**Entities to replace:**
* sensor.energy_monitor_power `Required`

```yaml
type: custom:mini-graph-card
name: Current Load
animate: true
decimals: 0
hours_to_show: 24
line_width: 1
points: false
points_per_hour: 6
entities:
  - sensor.energy_monitor_power
show:
  labels: true
  icon_adaptive_color: true
  extrema: false
  average: false
color_thresholds:
  - value: 1000
    color: '#0099ff'
  - value: 2000
    color: '#4caf50'
  - value: 4000
    color: '#ff9800'
  - value: 6000
    color: '#f44336'
icon: mdi:transmission-tower
card_mod:
  style:
    .header.flex .icon ha-icon:
      $: |
        ha-svg-icon {
          animation: blink 1s linear infinite;
          }
          @keyframes blink {
            50% {opacity: 0;}
            }
```