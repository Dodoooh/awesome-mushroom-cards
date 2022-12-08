# Animation 03

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3272?u=d0doooh)

### **Full Lovelance** <!-- {docsify-ignore} -->

Import the [animation-03.yaml](animation-03.yaml)

## Cards:

### Flash Animation

![](https://community-assets.home-assistant.io/original/4X/6/d/1/6d11a5cbe3a42ecbeb37bfa40fe8259a179f7e66.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:flash
icon_color: amber
primary: Flash
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: flash 4s linear infinite;
      }
      @keyframes flash {
        0%, 4%, 8%, 12%, 16%, 20%, 24%, 28%, 32%, 100% { transform: translate(0px,0px); }
        2% { transform: translate(-0.3px, 0px); }
        6% { transform: translate(0.3px, d 0px); }
        10% { transform: translate(-0.2px, 0px); }
        14% { transform: translate(0.2px, 0px); }
        18% { transform: translate(-0.2px, 0px); }
        22% { transform: translate(0.5px, 0px); }
        26% { transform: translate(-0.5px, 0px); }
        34% { transform: translate(-1px, 5px); --icon-color: rgb(var(--rgb-amber)); }
        38% { transform: translate(0px, 0px); --icon-color: rgb(var(--rgb-white)); }
        40% { --icon-color: rgb(var(--rgb-amber)); }
      }
```

### Charge Animation

![](https://community-assets.home-assistant.io/original/4X/f/7/b/f7bf1106d098a2209d87fb2a8e026e0a9e7ab629.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:lightning-bolt
icon_color: amber
primary: Charge
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: charge 1s linear infinite;
      }
      @keyframes charge {
        0%, 10%, 20%, 30%, 40%, 50%, 60%, 70%, 80%, 90%, 100% { transform: translate(0, 0); }
        5% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        15% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        25% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        35% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        45% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        55% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        65% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        75% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        85% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
        95% { transform: translate({{ range(-10, 10) | random / 10 }}px, {{ range(-10, 10) | random / 10 }}px); }
      }
```

### Double Rainbow Animation

![](https://community-assets.home-assistant.io/original/4X/7/c/2/7c223e70f708aae6a68bce582ea9f90c5c1f7356.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:looks
primary: Double Rainbow
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: double 3s linear infinite alternate;
      }
      @keyframes double {
        0% { clip-path: inset(0 98% 0 0); transform: rotateY(0deg); }
        12.5% { clip-path: polygon(0 22%, 0 75%, 50% 75%); }
        25% { clip-path: inset(0 50% 0 0); }
        37.5% { clip-path: polygon(0 0, 0 75%, 50% 75%, 100% 0); }
        50% { clip-path: inset(0 0 0 0); transform: rotateY(0deg); }
        50.1% { transform: rotateY(180deg); }
        62.5% { clip-path: polygon(0 0, 0 75%, 50% 75%, 100% 0); }
        75% { clip-path: inset(0 50% 0 0); }
        87.5% { clip-path: polygon(0 22%, 0 75%, 50% 75%); }
        100% { clip-path: inset(0 98% 0 0); transform: rotateY(180deg); }
      }
      .shape {
        --shape-animation: rainbow 40s linear infinite;
      }
      @keyframes rainbow {
        0%, 100% {--icon-color: rgb(var(--rgb-red)); --shape-color: rgb(var(--rgb-red), 0.2); }
        6.25% { --icon-color: rgb(var(--rgb-deep-orange)); --shape-color: rgb(var(--rgb-deep-orange), 0.2); }
        12.5% { --icon-color: rgb(var(--rgb-orange)); --shape-color: rgb(var(--rgb-orange), 0.2); }
        18.75% { --icon-color: rgb(var(--rgb-amber)); --shape-color: rgb(var(--rgb-amber), 0.2); }
        25% { --icon-color: rgb(var(--rgb-yellow)); --shape-color: rgb(var(--rgb-yellow), 0.2); }
        31.25% { --icon-color: rgb(var(--rgb-lime)); --shape-color: rgb(var(--rgb-lime), 0.2); }
        37.5% { --icon-color: rgb(var(--rgb-light-green)); --shape-color: rgb(var(--rgb-light-green), 0.2); }
        43.75% { --icon-color: rgb(var(--rgb-green)); --shape-color: rgb(var(--rgb-green), 0.2); }
        50% { --icon-color: rgb(var(--rgb-teal)); --shape-color: rgb(var(--rgb-teal), 0.2); }
        56.25% { --icon-color: rgb(var(--rgb-cyan)); --shape-color: rgb(var(--rgb-cyan), 0.2); }
        62.5% { --icon-color: rgb(var(--rgb-light-blue)); --shape-color: rgb(var(--rgb-light-blue), 0.2); }
        68.75% { --icon-color: rgb(var(--rgb-blue)); --shape-color: rgb(var(--rgb-blue), 0.2); }
        75% { --icon-color: rgb(var(--rgb-indigo)); --shape-color: rgb(var(--rgb-indigo), 0.2); }
        81.25% { --icon-color: rgb(var(--rgb-deep-purple)); --shape-color: rgb(var(--rgb-deep-purple), 0.2); }
        87.5% { --icon-color: rgb(var(--rgb-purple)); --shape-color: rgb(var(--rgb-purple), 0.2); }
        93.75% { --icon-color: rgb(var(--rgb-pink)); --shape-color: rgb(var(--rgb-pink), 0.2); }
      }
```

### Random Animation

![](https://community-assets.home-assistant.io/original/4X/5/3/1/53195e5a4fe8fb859af4be3642a999a852c5cdd0.png)

```yaml
type: custom:mushroom-template-card
icon: none
icon_color: red
primary: Random
card_mod:
  style: |
    :host {
      --card-mod-icon: mdi:dice-{{range(1, 6) | random}};
    }
```

### Sparkle Animation

![](https://community-assets.home-assistant.io/original/4X/e/e/a/eeaf902756a4ae4e25a5ff0780cc5d243052cb6d.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:shimmer
icon_color: amber
primary: Sparkle
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: stars 4s linear infinite;
      }
      .shape {
        --shape-color: rgba(var(--rgb-disabled), 0.2);
      }
      @keyframes stars {
        0%, 3.1%, 14.1%, 40.1%, 55.1% { clip-path: inset(0 0 0 0); }
        3%, 40% { clip-path: polygon(48% 100%, 48% 62%, 0 63%, 0 0, 100% 0, 99% 100%); }
        14% { clip-path: polygon(49% 45%, 48% 100%, 0 100%, 0 0, 100% 0, 100% 36%); }
        55% { clip-path: polygon(0 100%, 0 60%, 41% 65%, 49% 46%, 100% 44%, 100% 100%); }
      }
```

### Eeeew Animation

![](https://community-assets.home-assistant.io/original/4X/5/0/6/506ef33042b8f47e32a6df06be828befedc7254e.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:bacteria
icon_color: light-green
primary: Eeeew
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: wiggle 0.5s ease infinite;
        transform-origin: 80% 80%;
      }
      @keyframes wiggle {
        0%, 100% { transform: scale(1) rotate(1deg); }
        50% { transform: scale(1.04) rotate(-2deg); }
    .: |
      mushroom-shape-icon {
        display: flex;
        animation: spin 20s infinite;
      }
```

### Sunny Animation

![](https://community-assets.home-assistant.io/original/4X/0/7/b/07b07fb2775d1a91c3372df731249db94750c0d0.gif)

```yaml
type: custom:mushroom-template-card
primary: Sunny
icon: mdi:weather-sunny
icon_color: amber
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: sunny 8s ease-in-out infinite alternate;
      }
      @keyframes sunny {
        70% { transform: rotate(360deg) scale(1); }
        80% { transform: scale(1); }
        90% { transform: scale(1.15); }
        100% { transform: scale(1); }
      }
```

### Cloudy Animation

![](https://community-assets.home-assistant.io/original/4X/1/a/4/1a4175814efdcd3d7b07027d3a7b98155bab51f9.gif)

```yaml
type: custom:mushroom-template-card
primary: Cloudy
icon: mdi:weather-cloudy
icon_color: grey
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite;
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
```

### Rainy Animation

![](https://community-assets.home-assistant.io/original/4X/d/b/b/dbbd1d3e8d3113331bf6855fb7c648517193a4aa.gif)

```yaml
type: custom:mushroom-template-card
primary: Rainy
icon: mdi:weather-rainy
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, rain 1.5s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes rain {
        50% { clip-path: polygon(0 0, 100% 0, 100% 73%, 71% 73%, 50% 39%, 29% 73%, 0 73%); }
      }
```

### Pouring Animation

![](https://community-assets.home-assistant.io/original/4X/b/3/2/b32ef92f3eab7937d7644cfd606d420120774936.gif)

```yaml
type: custom:mushroom-template-card
primary: Pouring
icon: mdi:weather-pouring
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, rain 1s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes rain {
        0%, 50%, 100% { clip-path: inset(0 0 0 0); }
        25% { clip-path: polygon(0 0, 100% 0, 100% 83%, 54% 83%, 62% 47%, 47% 46%, 38% 83%, 0 83%); }
        75%  { clip-path: polygon(0 0, 100% 0, 100% 70%, 75% 70%, 80% 48%, 63% 48%, 54% 94%, 32% 94%, 46% 46%, 30% 46%, 23% 72%, 0 72%); }
      }
```

### Tornado Animation

![](https://community-assets.home-assistant.io/original/4X/2/7/4/27452f0c68db3a59c4343343407b0a535ff430ad.gif)

```yaml
type: custom:mushroom-template-card
primary: Tornado
icon: mdi:weather-tornado
icon_color: orange
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: tornado 3s ease-in-out infinite; 
      }
      @keyframes tornado {
        0%, 100% { transform: translateX(3px) rotateY(0deg); }
        0.1%, 45.1% { transform: rotateY(180deg); }
        30% { transform: translateX(-1px) rotateY(180deg); }
        30.1%, 75.1% { transform: rotateY(0deg); }
        45% { transform: translateX(1.5px) rotateY(0deg); }
        75% { transform: translateX(-3.2px) rotateY(180deg); }
      }
```

### Lightning Animation

![](https://community-assets.home-assistant.io/original/4X/6/d/f/6df3afb289c611e6dd06c555c39ba71ad7d5b38c.gif)

```yaml
type: custom:mushroom-template-card
primary: Lightning
icon: mdi:weather-lightning
icon_color: amber
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, lightning 4s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes lightning {
        10%, 15% { clip-path: polygon(0 0, 100% 0, 100% 100%, 47% 100%, 69% 55%, 66% 40%, 48% 39%, 24% 100%, 0 100%); transform: scale(1.1); }
        10.1%, 15.1% { clip-path: inset(0 0 0 0); transform: scale(1); }
      }
```

### Clear Night Animation

![](https://community-assets.home-assistant.io/original/4X/2/6/f/26faeae0e0d26a301fc6753546768297215789b9.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:weather-night
icon_color: amber
primary: Clear Night
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: moon 10s linear infinite, stars 5s linear infinite;
      }
      @keyframes moon {
        0%, 100% { transform: rotate(12deg); }
        30% { transform: rotate(-6deg); }
        45% { transform: rotate(8deg); }
        75% { transform: rotate(-10deg); }
      }
      @keyframes stars {
        0%, 3.1%, 14.1% { clip-path: inset(0 0 0 0); }
        3% { clip-path: polygon(1% 1%, 0% 99%, 99% 100%, 99% 62%, 68% 62%, 62% 44%, 76% 34%, 100% 34%, 99% 0%); }
        14% { clip-path: polygon(1% 1%, 0% 99%, 99% 100%, 100% 25%, 51% 45%, 38% 34%, 36% 0); }
      } 
```

### Windy Animation

![](https://community-assets.home-assistant.io/original/4X/0/2/0/0200f30f7a5f02c0a52e8671acc101a7e341ea0e.gif)

```yaml
type: custom:mushroom-template-card
primary: Windy
icon: mdi:weather-windy
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite; 
        transform-origin: 15% 50%
      }
      @keyframes cloudy {
        0%, 100% { transform: scaleX(1.2); }
        30% { transform: scaleX(0.9); }
        45% { transform: scaleX(1.1); }
        75% { transform: scaleX(0.8); }
      }
```

### Wind Animation

![](https://community-assets.home-assistant.io/original/4X/b/7/4/b74e80b6036dde158f12819a428574ce4529d5d2.gif)

```yaml
type: custom:mushroom-template-card
primary: Wind
icon: mdi:weather-windy-variant
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, wind 5s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes wind {
        0%, 50%, 100% { clip-path: inset(0 0 0 0); }
        25% { clip-path: inset(0 0 37% 0); }
      }
```

### Snow Animation

![](https://community-assets.home-assistant.io/original/4X/d/e/5/de5d519dc79320bcd8eb32f10381660cf5ce0225.gif)

```yaml
type: custom:mushroom-template-card
primary: Snow
icon: mdi:weather-snowy
icon_color: grey
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, snow 4s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes snow {
        50% { clip-path: polygon(0 0, 100% 0, 100% 100%, 65% 100%, 76% 73%, 57% 49%, 34% 56%, 26% 79%, 37% 100%, 0 100%); }
        51% { clip-path: inset(0 0 0 0); }
      }
```

### Hail Animation

![](https://community-assets.home-assistant.io/original/4X/3/8/e/38e02c8c2e2f85015364ec5c67412f62b6104483.gif)

```yaml
type: custom:mushroom-template-card
primary: Hail
icon: mdi:weather-hail
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, hail 2s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes hail {
        0%, 26%, 51%, 76%, 100% { clip-path: inset(0 0 0 0); }
        25% { clip-path: polygon(0 0, 100% 0, 100% 100%, 62% 100%, 47% 69%, 56% 55%, 43% 43%, 31% 58%, 48% 68%, 63% 100%, 0 100%); }
        50%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 62% 100%, 61% 86%, 74% 74%, 61% 60%, 46% 69%, 60% 87%, 63% 100%, 0 100%); }
        75%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 47% 100%, 56% 83%, 42% 68%, 27% 81%, 37% 100%, 0 100%); }
      }
```

### Hurricane Animation

![](https://community-assets.home-assistant.io/original/4X/e/c/4/ec4e56cb790436b8a9cfd21e29b5531970e888d8.gif)

```yaml
type: custom:mushroom-template-card
primary: Hurricane
icon: mdi:weather-hurricane
icon_color: red
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1.5s linear infinite reverse; 
      }
```

### Dust Animation

![](https://community-assets.home-assistant.io/original/4X/8/b/7/8b75b2c4281d15a6a40c3e43b11ecec2d22e34bc.gif)

```yaml
type: custom:mushroom-template-card
primary: Dust
icon: mdi:weather-dust
icon_color: brown
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: wind 10s ease-in-out infinite, dust 1s infinite; 
        transform-origin: 15% 50%
      }
      @keyframes wind {
        0%, 100% { transform: scaleX(1.2); }
        30% { transform: scaleX(0.9); }
        45% { transform: scaleX(1.1); }
        75% { transform: scaleX(0.8); }
      }
      @keyframes dust {
        0%, 21%, 41%, 61%, 81%, 100% { clip-path: inset(0 0 0 0); }
        20% { clip-path: polygon(0 0, 69% 0, 72% 27%, 100% 30%, 100% 100%, 0 100%); }
        40%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 57% 100%, 57% 79%, 0 79%); }
        60%  { clip-path: polygon(30% 0, 100% 0, 100% 100%, 0 100%, 0 28%, 30% 28%); }
        80%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%, 0 61%, 32% 62%, 32% 46%, 0 46%); }
      }
```

### Foggy Animation

![](https://community-assets.home-assistant.io/original/4X/5/2/0/520e0b016fd49c4e00af2473c81a1f9f6da3372e.gif)

```yaml
type: custom:mushroom-template-card
primary: Foggy
icon: mdi:weather-fog
icon_color: grey
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, fog 4s infinite; 
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes fog {
        0%, 26%, 76%, 100% { clip-path: inset(0 0 0 0); }
        25% { clip-path: polygon(0 0, 100% 0, 100% 59%, 60% 59%, 60% 74%, 100% 74%, 100% 100%, 0 100%); }
        75%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 26% 100%, 26% 76%, 0 76%); }
      }
```

### Partly Cloudy Animation

![](https://community-assets.home-assistant.io/original/4X/7/7/6/7762231e6bc4093266fdc0f342fd5e3a65a8685c.gif)

```yaml
type: custom:mushroom-template-card
primary: Cloudy
icon: mdi:weather-partly-cloudy
icon_color: amber
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: cloudy 10s ease-in-out infinite, sun 2s infinite;
      }
      @keyframes cloudy {
        0%, 100% { transform: translateX(3px); }
        30% { transform: translateX(-1px); }
        45% { transform: translateX(1.5px); }
        75% { transform: translateX(-3.2px); }
      }
      @keyframes sun {
        50% { clip-path: polygon(0 67%, 18% 55%, 16% 31%, 41% 12%, 67% 24%, 77% 59%, 100% 64%, 100% 100%, 0 100%); }
      }
```

### Fireplace Animation

![](https://community-assets.home-assistant.io/original/4X/a/1/a/a1a845b1fcf638c338fc944b55db2c3c9e6e0dd1.gif)

```yaml
type: custom:mushroom-template-card
primary: Fireplace
icon: mdi:fireplace
icon_color: red
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: fire 800ms infinite;
        transform-origin: 50% 85%;
      }
      @keyframes fire {
          0%, 19%, 23%, 39%, 43%, 49%, 53%, 69%, 73%, 89%, 93%, 100% { clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); }
          20%, 40%, 50%, 70%, 90% { clip-path: polygon(0 0, 100% 0, 100% 100%, 65% 99%, 66% 49%, 52% 44%, 33% 48%, 33% 82%, 66% 82%, 69% 100%, 0 100%); }
      }
```

### Washing Machine #2 Animation

![](https://community-assets.home-assistant.io/original/4X/1/0/4/104bea290004b27e7965734ff25c3fda5ee3da58.gif)

```yaml
type: custom:stack-in-card
cards:
  - type: custom:mushroom-template-card
    icon: mdi:washing-machine
    icon_color: orange
    primary: 'Washing Machine #2'
    card_mod:
      style:
        mushroom-shape-icon$: |
          ha-icon {
            --icon-animation: shake 400ms ease-in-out infinite;
            transform-origin: 50% 58%;
            clip-path: polygon(0 0, 0 100%, 35% 100%, 34% 68%, 60% 41%, 71% 56%, 65% 74%, 47% 79%, 32% 69%, 35% 100%, 100% 100%, 100% 0);
          }
          @keyframes shake {
            0%, 100% { transform: translate(0, 0) rotate(0); }
            20%  { transform: translate(0.4px, -0.4px) rotate(-4deg); }
            40%  { transform: translate(-0.4px, 0.4px) rotate(4deg); }
            60%  { transform: translate(0.4px, 0.4px) rotate(-4deg); }
            80%  { transform: translate(-0.4px, -0.4px) rotate(4deg); }
          }
  - type: custom:mushroom-template-card
    icon: mdi:washing-machine
    icon_color: orange
    card_mod:
      style:
        mushroom-shape-icon$: |
          ha-icon {
            --icon-animation: spin 1s linear infinite;
            transform-origin: 50% 58%;
            clip-path: circle(21.7% at 50% 58%);
          }
          .shape {
            --shape-color: none;
          }
        .: |
          ha-card {
            width: 66px;
            top: -66px;
          }
card_mod:
  style: |
    ha-card {
      height: 66px;
    }
```

### Pot Animation

![](https://community-assets.home-assistant.io/original/4X/2/b/b/2bbc92e6aada904e5fa86df065736a5e08651099.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:pot-steam
icon_color: grey
primary: Pot
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: steam 2s ease-in-out infinite;
      }
      @keyframes steam {
        0%, 100% { clip-path: inset(0 0 0 0); }
        50% { clip-path: inset(39% 0 0 0); }
      }
```

### Serenity Animation

![](https://community-assets.home-assistant.io/original/4X/9/5/e/95e4e17c4a6e7f5221aefe614b9ab2b57dfaf24a.gif)

```yaml
type: custom:mushroom-template-card
primary: Serenity
icon: mdi:scent
icon_color: green
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: wave 6s ease infinite;
      }
      @keyframes wave {
        50% { transform: rotatey(180deg); --icon-color: rgb(var(--rgb-cyan)); }
      }
      .shape {
        --shape-animation: color 6s ease infinite;
      }
      @keyframes color {
        50% { --shape-color: rgba(var(--rgb-cyan), 0.2); }
      }
```

### Music #1 Animation

![](https://community-assets.home-assistant.io/original/4X/f/d/7/fd7141d07aee7e96a4d491b7cd4d240309d44d55.gif)

```yaml
type: custom:mushroom-template-card
primary: 'Music #1'
icon: mdi:music
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: music 2s ease-in-out infinite alternate;
        transform-origin: 50% 100%
      }
      .shape {
        perspective: 7px;
      }
      @keyframes music {
        0%, 100% { transform: translateY(0px) scaleX(1); }
        20% { transform: translateY(2px) scaleX(0.9); }
        40% { transform: rotateY(10deg) rotateZ(-10deg); }
        60% { transform: translateY(-4px) scaleX(1.1); }
        80% { transform: rotateY(-10deg) rotateZ(10deg); }
      }
```

### Music #2 Animation

![](https://community-assets.home-assistant.io/original/4X/9/2/c/92cd32a540a0cf9da905cd0dd4ee579de824cc03.gif)

```yaml
type: custom:mushroom-template-card
primary: 'Music #2'
icon: mdi:music
icon_color: blue
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: beat 1.3s ease-out infinite both;
        transform-origin: 50% 80%;
      }
      @keyframes beat {
        0% { transform: scale(1); }
        10% { transform: scale(1.1); }
        17% { transform: scale(1.05); }
        33% { transform: scale(1.25); }
        60% { transform: scale(1); }
      }
```

### Playlist Animation

![](https://community-assets.home-assistant.io/original/4X/a/3/4/a341792e86d120b3acfd49db0e284bc8be405d0c.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:format-list-bulleted-square
icon_color: purple
primary: Playlist
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: clip 2s steps(4) infinite;
      }
      @keyframes clip {
        0% { clip-path: inset(0 0 85% 0); }
        100% { clip-path: inset(0 0 -5% 0); }
      }
```

### Grain Animation

![](https://community-assets.home-assistant.io/original/4X/1/e/8/1e80c56177ada29f5c4f060b04d6f5c53366f52e.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:grain
icon_color: brown
primary: Grain
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: flip 1s steps(1) infinite;
      }
      @keyframes flip {
        50% { transform: rotateY(180deg); }
      }
```

### Focus Animation

![](https://community-assets.home-assistant.io/original/4X/b/f/3/bf3957c092a6907aaabbae81d62a66c0807f50c2.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:bullseye
icon_color: purple
primary: Focus
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: focus 4s linear infinite alternate;
      }
      @keyframes focus {
        50% { filter: blur(10px); }
      }
```

### Access Point Animation

![](https://community-assets.home-assistant.io/original/4X/4/8/a/48aca787b909e564162ae6c580a698197168baa9.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:access-point
icon_color: teal
primary: Access Point
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: clip 1.5s infinite;
      }
      @keyframes clip {
        0% { clip-path: circle(13.0% at 50% 50%); }
        100% { clip-path: circle(50.0% at 50% 50%); }
      }
      .shape {
        --shape-animation: ping 1.5s infinite;
      }
      @keyframes ping {
        0% { box-shadow: 0 0 1px 1px rgba(var(--rgb-teal), 0.3) inset; }
        50% { box-shadow: 0 0 5px 15px transparent inset; }
        51% { box-shadow: 0 0 1px 1px rgba(var(--rgb-teal), 0.3); }
        100% { box-shadow: 0 0 5px 15px transparent; }
      }
```

### Alert Animation

![](https://community-assets.home-assistant.io/original/4X/b/6/7/b67fd007439de054720e5b44fad19552eb1083ff.gif)

```yaml
type: custom:mushroom-template-card
primary: Alert!
icon: mdi:fire
icon_color: red
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        --shape-animation: ping 1.5s infinite, blink 1.5s ease-in-out infinite;;
      }
      @keyframes ping {
        0% { box-shadow: 0 0 0 0 rgba(var(--rgb-red), 0.7); }
        100% { box-shadow: 0 0 5px 15px transparent; }
      }
      @keyframes blink {
        100% {opacity: 0;}
      }
```

### Record Animation

![](https://community-assets.home-assistant.io/original/4X/7/9/d/79d9dc50f0fe12ac0ba8662689446f8a4c68a1e1.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:record-circle
icon_color: cyan
primary: Record
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        background: linear-gradient(-45deg, rgba(var(--rgb-black), 0.4) 0%, rgba(var(--rgb-black), 0.6) 50%, rgba(var(--rgb-black), 0.4) 100%);
        --shape-animation: spin 400ms linear infinite;
        --shape-color: none;
      }
```

### Heart Animation

![](https://community-assets.home-assistant.io/original/4X/5/e/f/5efec1a11befce93cc58964996c7b6c45debcae7.gif)

```yaml
type: custom:mushroom-template-card
primary: Heart
icon: mdi:heart
icon_color: red
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        --icon-animation: beat 1.3s ease-out infinite both;
        transform-origin: 50% 60%;
        --shape-animation: heart 1.3s ease-out infinite both;
      }
      @keyframes beat {
        0% { transform: scale(1); }
        10% { transform: scale(1.1); }
        17% { transform: scale(1.05); }
        33% { transform: scale(1.25); }
        60% { transform: scale(1); }
      }
      @keyframes heart {
        0% { box-shadow: 0 0 0 0 rgba(var(--rgb-red), 0.2); }
        10% { box-shadow: 0 0 5px 5px transparent; }
        17% { box-shadow: 0 0 0 0 rgba(var(--rgb-red), 0.2); }
        33% { box-shadow: 0 0 5px 5px transparent; }
        60% { box-shadow: 0 0 0 0 rgba(var(--rgb-red), 0.2); }
      }
```

### Play Animation

![](https://community-assets.home-assistant.io/original/4X/4/d/3/4d37c01ca9f1db1350357a6908a093a4bd94a27b.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:play
icon_color: orange
primary: Play
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 4s steps(4) infinite;
      }
```

### Christmas Tree Animation

![](https://community-assets.home-assistant.io/original/4X/4/a/0/4a05840bddc1320d8be1f5056259e3be2639b7a3.gif)

```yaml
type: custom:stack-in-card
cards:
  - type: custom:mushroom-template-card
    icon: mdi:pine-tree
    icon_color: green
    primary: Christmas Tree
  - type: custom:mushroom-template-card
    icon: mdi:star-four-points
    icon_color: yellow
    primary: Star
    card_mod:
      style:
        mushroom-shape-icon$: |
          ha-icon {
            --icon-animation: star 8s ease infinite alternate;
          }
          @keyframes star {
            0%, 100% { transform: translateY(-10px) rotate(0deg) scale(0.4); }
            50% { transform: translateY(-10px) rotate(360deg) scale(0.6); }
          }
          .shape {
            --shape-color: none;
          }
        .: |
          ha-card {
            width: 66px;
            top: -66px;
          }
  - type: custom:mushroom-template-card
    icon: mdi:gift
    icon_color: red
    card_mod:
      style:
        mushroom-shape-icon$: |
          ha-icon {
            --icon-animation: surprise 4s ease infinite;
          }
          @keyframes surprise {
            0%, 20%, 100% { transform: translateY(0); }
            2.5% { transform: translateY(-2px) rotate(-27deg); }
            5% { transform: translateY(-2px) rotate(21deg); }
            7.5% { transform: translateY(-2px) rotate(-15deg); }
            10% { transform: translateY(-2px) rotate(9deg); }
            12.5% { transform: translateY(0); }
            15% { transform: translateY(-1.2px) }
          }
          .shape {
            --shape-color: none;
            --icon-size: 20px;
            top: 16px;
            left: 18px;
          }
        .: |
          ha-card {
            width: 66px;
            top: -132px;
          }
card_mod:
  style: |
    ha-card {
      height: 66px;
    }
```

### Doggy Animation

![](https://community-assets.home-assistant.io/original/4X/7/7/f/77f52d44976fcded534fc8b8d8ef14003dd84304.gif)

```yaml
type: custom:mushroom-template-card
primary: Doggy
icon: mdi:dog
icon_color: brown
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: huh 4s ease infinite;
        transform-origin: 50% 60%;
      }
      @keyframes huh {
        0%, 10%, 75%, 100% { transform: rotate(0deg); }
        15% { transform: rotate(-25deg); }
        30%, 35% { transform: rotate(-40deg); }
        50% { transform: rotate(12deg); }
        65% { transform: rotate(-8deg); }
      }
```
