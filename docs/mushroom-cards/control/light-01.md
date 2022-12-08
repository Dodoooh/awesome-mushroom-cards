# Light 01

## Cards:<!-- {docsify-ignore} -->

### Full Color Light Card

Author: [theandouz](https://community.home-assistant.io/u/theandouz) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3740?u=d0doooh)

![](https://community-assets.home-assistant.io/original/4X/5/7/2/572525129a2d71ac222f5ced95ddef6a1659efd8.png)

**Entities to replace:**
* light.dummy_light_01 `Required`

```yaml
type: custom:mushroom-light-card
name: Lamp
entity: light.dummy_light_01
icon: mdi:lamp
use_light_color: true
show_brightness_control: true
show_color_control: true
show_color_temp_control: true
collapsible_controls: false
card_mod:
  style: |
    ha-card {
      {% set r = state_attr(config.entity, 'rgb_color')[0] %}
      {% set g = state_attr(config.entity, 'rgb_color')[1] %}
      {% set b = state_attr(config.entity, 'rgb_color')[2] %}
      {% if is_state(config.entity, 'on') %}
          background: rgba({{r}}, {{g}}, {{b}},0.1);
          --primary-text-color: rgb({{r}}, {{g}}, {{b}});
          --secondary-text-color: rgba({{r}}, {{g}}, {{b}},0.5);
      {% endif %}
    }
```