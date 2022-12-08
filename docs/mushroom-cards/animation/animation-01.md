# Animation 01

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3240?u=d0doooh)

### **Full Lovelance** <!-- {docsify-ignore} -->

Import the [animation-01.yaml](animation-01.yaml)

## Built-in Mushroom Animations

There are two built-in animations for Mushroom cards that can be used without specifying any @keyframes. These are spin, which is used for the rotating fan, and pulse, which fades in and out.

### Spin Animation

![](https://community-assets.home-assistant.io/original/4X/d/3/f/d3f53da8f48271dc66c0df4794aa6326d55694d3.gif)

```yaml
type: custom:mushroom-template-card
primary: Spin
icon: mdi:fan
icon_color: teal
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1s linear infinite;
      }
```

### Pulse Animation

![](https://community-assets.home-assistant.io/original/4X/9/8/2/982a92229da3e076896f8018e99e3b8f3e0fe1a1.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:pulse
icon_color: red
primary: Pulse
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: pulse 2s ease-in-out infinite;
      }
```

## Mushroom Card Icon Animations

### Boil Animation

![](https://community-assets.home-assistant.io/original/4X/6/0/9/609281341829cf92afb3d0cf3be913f95e9ccef0.gif)

```yaml
type: custom:mushroom-template-card
primary: Boil
icon: mdi:kettle-steam
icon_color: red
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: boil 500ms infinite;
      }
      @keyframes boil {
        0%, 100% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        10% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); clip-path: polygon(0 0, 66% 10%, 67% 30%, 88% 52%, 100% 100%, 0 100%); }
        20% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        30% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        40% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        50% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        60% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        70% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        80% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
        90% { transform: translate({{ range(-20, 20) | random / 10 }}px, {{ range(-20, 20) | random / 10 }}px) rotate({{ range(-15, 15) | random }}deg); }
      }
```

### Fire Animation

![](https://community-assets.home-assistant.io/original/4X/a/f/3/af37c70fc4773093a6b2c882a422e49875321b4c.gif)

```yaml
type: custom:mushroom-template-card
primary: Fire
icon: mdi:fire
icon_color: red
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: fire 1.5s infinite;
        transform-origin: 50% 85%;
      }
      @keyframes fire {
          0% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          5% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          10% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          15% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          20% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          25% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          30% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          35% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          40% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          45% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          50% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          55% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          60% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          65% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          70% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          75% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          80% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          85% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          90% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
          95% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-red)); opacity: {{range(7, 10) | random / 10}}; }
          100% { transform: rotate({{range(-20, 20) | random / 10}}deg) scaleY({{range(9, 12) | random / 10}}); color: rgb(var(--rgb-deep-orange)); opacity: {{range(7, 10) | random / 10}}; }
      }
```

### Shower Animation

![](https://community-assets.home-assistant.io/original/4X/d/c/4/dc479d6793e2162f9d96335f8a680779e573ed5e.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:shower-head
icon_color: light-blue
primary: Shower
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: clip 0.7s ease-out infinite;
      }
      @keyframes clip {
        0% {clip-path: inset(0 0 45% 0); }
        100% { clip-path: inset(0 0 0 0); }
      }
```

### Sprinkler Animation

![](https://community-assets.home-assistant.io/original/4X/5/5/d/55da54c7f686cf09d7b97f1e9938007ae6657af5.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:sprinkler
icon_color: cyan
primary: Sprinkler
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon { 
        --icon-animation: sprinkle 2s linear infinite;
        transform-origin: 29% 88%; 
      }
      @keyframes sprinkle {
        0%, 15%, 30%, 45%, 60%, 100% { clip-path: inset(0 55% 0 0); transform: rotate(0deg); }
        1%, 16%, 31%, 46% { clip-path: inset(0 0 0 0); transform: rotate(-10deg); }
        6%, 21%, 36%, 51% { transform: rotate(2deg); }
      }
```

### Washing Machine Animation

![](https://community-assets.home-assistant.io/original/4X/6/e/f/6ef9912646d6d1aa28954bc7789e398189246ebb.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:washing-machine
icon_color: amber
primary: Washing Machine
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: shake 400ms ease-in-out infinite, drum 2s ease infinite;
        transform-origin: 50% 110%;
      }
      @keyframes shake {
        0%, 100% { transform: translate(0, 0) rotate(0); }
        20%  { transform: translate(0.4px, -0.4px) rotate(-4deg); }
        40%  { transform: translate(-0.4px, 0.4px) rotate(4deg); }
        60%  { transform: translate(0.4px, 0.4px) rotate(-4deg); }
        80%  { transform: translate(-0.4px, -0.4px) rotate(4deg); }
      }
      @keyframes drum {
        50%  { clip-path: polygon(0 0, 0 100%, 35% 100%, 34% 68%, 60% 41%, 71% 56%, 65% 74%, 47% 79%, 32% 69%, 35% 100%, 100% 100%, 100% 0); }
      }
```

### Dishwasher Animation

![](https://community-assets.home-assistant.io/original/4X/7/f/5/7f51aaf77ba9a82347f189c719b4ad50faef7e0e.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:dishwasher
icon_color: blue
primary: Dishwasher
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: bounce 1.5s ease-in-out infinite, wash 1s ease-in-out infinite;
        transform-origin: 50% 75%;
      }
      @keyframes bounce {
        0%, 20%, 50%, 80%, 100% {transform: translateY(0); } 
        40% { transform: translateY(-1.2px) rotate(5deg); } 
        60% { transform: translateY(-1.1px) rotate(-4deg); } 
      } 
      @keyframes wash {
        50%  { clip-path: polygon(0 0, 0 100%, 35% 100%, 36% 74%, 31% 43%, 61% 40%, 71% 69%, 62% 78%, 36% 73%, 35% 100%, 100% 100%, 100% 0); }
      }
```

### Dryer Animation

![](https://community-assets.home-assistant.io/original/4X/3/a/d/3adf85bdedd27c0458000c731206e5f1ec23a64d.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:tumble-dryer
icon_color: teal
primary: Dryer
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: shake 400ms ease-in-out infinite, drum 1s infinite;
        transform-origin: 50% 65%;
      }
      @keyframes shake {
        0%, 100% { transform: rotate(4deg); }
        50%  { transform: rotate(-4deg); }
      }
      @keyframes drum {
        50%  { clip-path: polygon(0 0, 0 100%, 35% 100%, 36% 74%, 31% 43%, 61% 40%, 71% 69%, 62% 78%, 36% 73%, 35% 100%, 100% 100%, 100% 0); }
      }
```

### Ding Animation

![](https://community-assets.home-assistant.io/original/4X/c/8/3/c83ffd45d459d68021647bd3221093ddd04b9bf8.gif)

```yaml
type: custom:mushroom-template-card
primary: Ding
icon: mdi:bell-ring
icon_color: indigo
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: ring 4s linear infinite;
        transform-origin: 50% 15%;
      }
      @keyframes ring {
        0% { transform: rotate(0); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        2% { transform: rotate(30deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        6% { transform: rotate(-28deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        10% { transform: rotate(34deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        14% { transform: rotate(-32deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        18% { transform: rotate(30deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        22% { transform: rotate(-28deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        26% { transform: rotate(26deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        30% { transform: rotate(-24deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        34% { transform: rotate(22deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        38% { transform: rotate(-20deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        42% { transform: rotate(18deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        46% { transform: rotate(-16deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        50% { transform: rotate(14deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        54% { transform: rotate(-12deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        58% { transform: rotate(10deg); clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%); }
        62% { transform: rotate(-8deg); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
        66% { transform: rotate(6deg); }
        70% { transform: rotate(-4deg); }
        74% { transform: rotate(2deg); }
        78% { transform: rotate(-1deg); }
        82% { transform: rotate(1deg); }
        86% { transform: rotate(0); }
        100% { transform: rotate(0); clip-path: polygon(0 50%, 0 100%, 100% 100%, 100% 50%, 85% 50%, 80% 30%, 60% 5%, 40% 5%, 20% 30%, 15% 50%); }
      }
```

### Alarm Animation

![](https://community-assets.home-assistant.io/original/4X/5/6/4/564de8475f9dbfed0343f4613b64f15bd1d3aefc.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:alarm
icon_color: red
primary: Alarm
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: alarm 0.8s ease infinite;
      }
      @keyframes alarm {
        0%, 80%, 100% { transform: translateY(0); }
        10% { transform: translateY(-2px) rotate(-27deg); }
        20% { transform: translateY(-2px) rotate(21deg); }
        30% { transform: translateY(-2px) rotate(-15deg); }
        40% { transform: translateY(-2px) rotate(9deg); }
        50% { transform: translateY(0); }
        60% { transform: translateY(-1.2px) }
      }
```

### Rocket Man Animation

![](https://community-assets.home-assistant.io/original/4X/e/7/2/e72d711fba3217a43e512fdd62e85c6444a937d4.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:rocket-launch
icon_color: deep-orange
primary: Rocket Man
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: thrust 100ms infinite, motion 3s ease-in-out infinite;
      }
      @keyframes thrust {
        0% { clip-path: polygon(0 0, 0 47%, 22% 57%, 28% 63%, 0 91%, 11% 100%, 37% 73%, 45% 77%, 55% 100%, 100% 100%, 100% 0%); }
        33% { clip-path: polygon(0 0, 0 47%, 24% 59%, 42% 76%, 54% 100%, 100% 100%, 100% 0); }
        66% { clip-path: polygon(0 0, 0 92%, 28% 64%, 36% 72%, 9% 100%, 100% 100%, 100% 0%); }
      }
      @keyframes motion {
        0%, 100% { transform: translateY(-2px) translateX(-3px); }
        50% { transform: translateY(3px) translateX(2px); }
      }
```

### Fountain Animation

![](https://community-assets.home-assistant.io/original/4X/3/d/3/3d31fcbfb8df0ff02adc61584753f12a06a366a3.gif)

```yaml
type: custom:mushroom-template-card
primary: Fountain
icon: mdi:fountain
icon_color: light-blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: fountain 1.5s ease infinite;
      }
      @keyframes fountain {
        0%, 100 { clip-path: polygon(0 100%, 0 0, 100% 0, 100% 100%); }
        50% { clip-path: polygon(0 100%, 0 47%, 100% 47%, 100% 100%); }
        60% { clip-path: polygon(0 100%, 100% 100%, 100% 37%, 79% 36%, 71% 21%, 56% 25%, 44% 25%, 31% 20%, 20% 36%, 0 36%); }
        70% { clip-path: polygon(0 100%, 100% 100%, 100% 36%, 79% 36%, 71% 22%, 81% 1%, 24% 0, 31% 21%, 20% 36%, 0 36%); }
        80% { clip-path: polygon(0 100%, 100% 100%, 100% 36%, 79% 36%, 76% 28%, 100% 0, 0 0, 23% 28%, 20% 36%, 0 36%); }
      }
```

### Motion Animation

![](https://community-assets.home-assistant.io/original/4X/7/2/7/72721407d022e7334438248a7e6d34f198884205.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:motion-sensor
icon_color: blue
primary: Motion
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: clip 2s linear infinite;
      }
      @keyframes clip {
        50% { clip-path: polygon(0 0, 55% 0, 100% 100%, 0 100%); }
      }
      .shape {
        --shape-animation: motion 2s linear infinite;
      }
      @keyframes motion {
        0%, 100% { --shape-color: rgba(var(--rgb-blue), 0.3); }
        50% { --shape-color: rgba(var(--rgb-blue), 0.2); }
      }
```

### Cog Animation

![](https://community-assets.home-assistant.io/original/4X/4/9/4/494ea70ef260da14132f4e2bd3420cd5253d3c40.gif)

```yaml
type: custom:mushroom-template-card
primary: Cog
icon: mdi:cog
icon_color: grey
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1.5s steps(5) infinite;
      }
```

### Signal Animation

![](https://community-assets.home-assistant.io/original/4X/9/5/4/954a4c2549cff5fb2fd2c347298edc2c73b4c63a.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:wifi
icon_color: green
primary: Signal
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: clip 2s steps(1) infinite;
      }
      @keyframes clip {
        0% { clip-path: circle(0% at 50% 85%); }
        20% { clip-path: circle(30% at 50% 85%); }
        40% { clip-path: circle(55% at 50% 85%); }
        60% { clip-path: circle(80% at 50% 85%); }
      }
      .shape {
        --shape-animation: ping 2s infinite;
      }
      @keyframes ping {
        60% { box-shadow: 0 0 0 0 rgba(var(--rgb-green), 0.7); }
        100% { box-shadow: 0 0 5px 15px transparent; }
      }
```

### Alert Animation

![](https://community-assets.home-assistant.io/original/4X/c/2/7/c27716587392841cf1aa1950a6bdd4811f9ba3dc.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:alarm-light
icon_color: red
primary: Alert
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: alert 0.8s infinite;
      }
      @keyframes alert {
        0%, 100% { color: rgb(var(--rgb-orange)); }
        50% { clip-path: polygon(0% 55%, 25% 55%, 25% 35%, 35% 25%, 50% 18%, 65% 20%, 75% 35%, 75% 55%, 100% 55%, 100% 100%, 0 100%); color: rgb(var(--rgb-red)); }
      }
      .shape {
        --shape-animation: alert-shape 0.8s infinite;
      }
      @keyframes alert-shape {
        0%, 100% { --shape-color: rgba(var(--rgb-orange), 0.2); }
        60% { --shape-color: rgba(var(--rgb-red), 0.2); }
      }
```

### Console Animation

![](https://community-assets.home-assistant.io/original/4X/2/e/4/2e4e2805526f7cb0e910f74986967c79d86d4132.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:console-line
icon_color: grey
primary: Console
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: console 1s infinite;
      }
      @keyframes console {
        50% { clip-path: polygon(0 0, 100% 0, 24% 100%, 0 100%); } 
      } 
```

### Keypad Animation

![](https://community-assets.home-assistant.io/original/4X/5/8/d/58dc5463c94e13bfa2298c7e1f0f0abb48dc1f85.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:dialpad
icon_color: blue
primary: Keypad
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: pin 4s infinite;
        transform-origin: 50% 75%;
      }
      @keyframes pin {
        0%, 15%, 25%, 35%, 45%, 55% { clip-path: inset(0 0 0 0); }
        10% { clip-path: polygon(0% 100%, 1% 23%, 36% 23%, 36% 0%, 100% 0, 100% 100%); } 
        20% { clip-path: polygon(0% 100%, 0 0, 62% 0, 61% 25%, 100% 24%, 100% 100%); } 
        30% { clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%, 0 25%, 36% 25%, 37% 50%, 63% 49%, 62% 26%, 0 25%); } 
        40% { clip-path: polygon(0 51%, 0 0, 100% 0, 100% 100%, 36% 100%, 37% 51%); } 
        50% { clip-path: polygon(0 100%, 0 0, 100% 0, 100% 50%, 64% 50%, 64% 100%); } 
      } 
      .shape {
        --shape-animation: ping 4s infinite;
      }
      @keyframes ping {
        55% { box-shadow: 0 0 1px 0px rgba(var(--rgb-blue), 0.3) inset; }
        100% { box-shadow: 0 0 5px 15px transparent inset; }
      }
```

### Eye Animation

![](https://community-assets.home-assistant.io/original/4X/2/d/6/2d6cd1fa8c55c55393e2883fa47089a3df073678.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:eye
icon_color: blue
primary: Eye
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: wink 4s ease-in-out infinite;
      }
      @keyframes wink {
        0%, 100% { transform: scale(1, 1); }
        19% { transform: scale(1.05, 0.6); }
        20% { clip-path: polygon(0 100%, 100% 100%, 100% 49%, 86% 51%, 79% 59%, 70% 66%, 57% 71%, 43% 71%, 29% 65%, 21% 57%, 13% 49%, 0 49%); }
        25% { transform: scale(1, 1); }
        28% { transform: scale(0.95, 1.05); }
        30% { clip-path: inset(0 0 0 0); }
      }
```

### Camera #1 Animation

<figure><img src="https://community-assets.home-assistant.io/original/4X/4/9/0/49002210f9fef06f48f37e71e7f7f21ac9c99ace.gif" alt=""><figcaption></figcaption></figure>

```yaml
type: custom:mushroom-template-card
icon: mdi:cctv
icon_color: deep-purple
primary: 'Camera #1'
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: flip 8s ease-in-out infinite alternate;
      }
      @keyframes flip {
        50% { transform: rotateY(180deg); }
      }
```

### Camera #2 Animation

![](https://community-assets.home-assistant.io/original/4X/7/9/0/790b0fa0ebcb0eb80dc77c7a2d5b9caed6304d74.gif)

```yaml
type: custom:mushroom-template-card
primary: 'Camera #2'
icon: mdi:cctv
icon_color: deep-purple
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: scan 5s ease-in-out infinite;
        transform-origin: 90% 80%
      }
      @keyframes scan {
        0%, 100% { transform: rotate(20deg); }
        50% { transform: rotate(-15deg); }
      }
```

### Battery #1 Animation

![](https://community-assets.home-assistant.io/original/4X/d/3/0/d30cd69a0df54b0e3f5ec88eef18d128378f0fac.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:battery
icon_color: green
primary: 'Battery #1'
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: charge 3s linear infinite;
      }
      @keyframes charge {
        0%, 80% { clip-path: inset(0 0 0 0); }
        10% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 84%, 34% 84%, 34% 100%, 100% 100%, 100% 0%); }
        20% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 74%, 34% 74%, 34% 100%, 100% 100%, 100% 0%); }
        30% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 64%, 34% 64%, 34% 100%, 100% 100%, 100% 0%); }
        40% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 54%, 34% 54%, 34% 100%, 100% 100%, 100% 0%); }
        50% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 44%, 34% 44%, 34% 100%, 100% 100%, 100% 0%); }
        60% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 34%, 34% 34%, 34% 100%, 100% 100%, 100% 0%); }
        70% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 24%, 34% 24%, 34% 100%, 100% 100%, 100% 0%); }
      }
```

### Battery #2 Animation

![](https://community-assets.home-assistant.io/original/4X/7/d/b/7db0df10bcde17b07f8798f3e213fdee6f34fd6d.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:battery-high
icon_color: green
primary: 'Battery #2'
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: charge 3s steps(1) infinite;
      }
      @keyframes charge {
        0% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 84%, 34% 84%, 34% 100%, 100% 100%, 100% 0%); }
        20% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 64%, 34% 64%, 34% 100%, 100% 100%, 100% 0%); }
        40% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 44%, 34% 44%, 34% 100%, 100% 100%, 100% 0%); }
        60% { clip-path: polygon(0% 0%, 0% 100%, 34% 100%, 34% 24%, 67% 24%, 67% 24%, 34% 24%, 34% 100%, 100% 100%, 100% 0%); }
      }
```

### Wrench Animation

![](https://community-assets.home-assistant.io/original/4X/8/4/a/84affb194f31b6f5b85636ddea3ead4728df5bf2.gif)

```yaml
type: custom:mushroom-template-card
primary: Wrench
icon: mdi:wrench
icon_color: grey
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: tighten 1.5s ease-in-out infinite;
        transform-origin: 31% 31%
      }
      @keyframes tighten {
        0%, 100% { transform: rotate(-20deg); }
        80% { transform: rotate(15deg); }
      }
```
