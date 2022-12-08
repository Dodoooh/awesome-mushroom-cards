# Animation 02

Author: [rhysb](https://community.home-assistant.io/u/rhysb) | [HA Community](https://community.home-assistant.io/t/mushroom-cards-build-a-beautiful-dashboard-easily/388590/3256?u=d0doooh)

### **Full Lovelance** <!-- {docsify-ignore} -->

Import the [animation-02.yaml](animation-02.yaml)

## Title Cards:

### Mushroom Title Animations

These ones run once to transition in the Mushroom Title.

### Typewriter Animation

![](https://community-assets.home-assistant.io/original/4X/e/4/c/e4cab18eeed2d07ca217d2d2090dd43cdd804a4f.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom.
  subtitle: Typewriter
card_mod:
  style:
    mushroom-title-card$: |
      h1 {
        width: 9ch;
        animation: typing 5s steps(9), cursor 0.25s step-end 30 alternate;
        overflow: hidden;
        border-right: 2px solid transparent;
        font-family: monospace;
      }
       @keyframes typing {
        0% { width: 0; }
      }
      @keyframes cursor {
        50% { border-color: var(--primary-text-color); }
      }
```

### Scale-in Animation

![](https://community-assets.home-assistant.io/original/4X/d/5/3/d53635f722d61e341dfeca012f7a19a164ee9649.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom 🍄
  subtitle: Scale-in
card_mod:
  style:
    mushroom-title-card$: |
      * {
          animation: scale-in 1s;
          transform-origin: 15%;
      }
      @keyframes scale-in {
        0% { transform: scale(0); opacity: 0; }
        100% { transform: scale(1); opacity: 1; }
      }
```

### Fade-in Animation

![](https://community-assets.home-assistant.io/original/4X/b/6/d/b6d7c0bea8c3973c104cfcc1c38b49df469ed99a.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom 🍄
  subtitle: Fade-in
card_mod:
  style:
    mushroom-title-card$: |
      * {
        animation: fade 1s ease-in;
      }
      @keyframes fade {
        0% { opacity: 0; }
        100% { opacity: 1; }
      }
```

### Focus Animation

![](https://community-assets.home-assistant.io/original/4X/0/0/9/009cbf14337dfd517f058dd7bd6864b2566a009e.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom 🍄
  subtitle: Focus
card_mod:
  style:
    mushroom-title-card$: |
      * {
        animation: focus 1.5s;
      }
      @keyframes focus {
        0% { filter: blur(10px); opacity: 0; }
      }
```

### Drop-in Animation

![](https://community-assets.home-assistant.io/original/4X/e/d/2/ed2cbb850b40d947605b7d6cc562f247d3f44465.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom 🍄
  subtitle: Drop-in
card_mod:
  style:
    mushroom-title-card$: |
      * {
        animation: drop-in 1.1s both;
      }
      @keyframes drop-in {
        0% { transform: translateY(-400px); animation-timing-function: ease-in; filter: blur(40px); opacity: 0; }
        38% { transform: translateY(0); animation-timing-function: ease-out; filter: blur(0); opacity: 1; }
        55% { transform: translateY(-16px); animation-timing-function: ease-in; }
        72% { transform: translateY(0); animation-timing-function: ease-out; }
        81% { transform: translateY(-7px); animation-timing-function: ease-in; }
        90% { transform: translateY(0); animation-timing-function: ease-out; }
        95% { transform: translateY(-2px); animation-timing-function: ease-in; }
        100% { transform: translateY(0); animation-timing-function: ease-out; }
      }
```

### Slide-in Animation

![](https://community-assets.home-assistant.io/original/4X/c/5/d/c5dd82318205e747314e18496ea5881ec3572ff9.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom 🍄
  subtitle: Slide-in
card_mod:
  style:
    mushroom-title-card$: |
      * {
        animation: slide-in 1.1s both;
      }
      @keyframes slide-in {
        0% { transform: translateX(600px) scaleX(2.5) scaleY(0.2); animation-timing-function: ease-in; filter: blur(40px); opacity: 0; }
        38% { transform: translateX(0) scaleY(1) scaleX(1); animation-timing-function: ease-out; filter: blur(0); opacity: 1; }
        55% { transform: translateX(68px) scaleY(1.1) scaleX(0.95); animation-timing-function: ease-in; }
        72% { transform: translateX(0) scaleY(1) scaleX(1); animation-timing-function: ease-out; }
        81% { transform: translateX(32px) scaleY(1.05) scaleX(0.98); animation-timing-function: ease-in; }
        90% { transform: translateX(0) scaleY(1) scaleX(1); animation-timing-function: ease-out; }
        95% { transform: translateX(8px); animation-timing-function: ease-in; }
        100% { transform: translateX(0); animation-timing-function: ease-out; }
      }
```

### Flicker Animation

![](https://community-assets.home-assistant.io/original/4X/1/0/d/10d4a3e8787071c750a2558eeef19815a7d00113.gif)

```yaml
type: custom:mod-card
card:
  type: custom:mushroom-title-card
  title: Mushroom 🍄
  subtitle: Flicker
card_mod:
  style:
    mushroom-title-card$: |
      * {
        animation: flicker 1.1s both;
      }
      @keyframes flicker {
        0%, 10%, 10.2%, 20%, 20.6%, 30%, 30.6%, 45%, 55.1%, 57%, 60.1%, 65%, 75.1%, 77%, 85.1%, 86% { opacity: 0; }
        10.1%, 20.1%, 30.1%, 30.5%, 45.1%, 50%, 55%, 57.1%, 60%, 65.1%, 75%, 77.1%, 85%, 86.1%, 100% { opacity: 1; }
      }
```

## Mushroom Spinner Animations

### Comet Spinner

![](https://community-assets.home-assistant.io/original/4X/4/9/e/49e270bf6267e7dacdd90a3d768a534bd83abade.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Comet
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        border-right: 4px solid;
        border-bottom: 4px solid transparent;
        --shape-animation: spin 1s linear infinite, comet 10s infinite;
        --shape-color: none;
        --icon-size: 38px;
      }
      @keyframes comet {
        0% { border-right-color: rgb(var(--rgb-red)); }
        6.25% { border-right-color: rgb(var(--rgb-deep-orange)); }
        12.5% { border-right-color: rgb(var(--rgb-orange)); }
        18.75% { border-right-color: rgb(var(--rgb-amber)); }
        25% { border-right-color: rgb(var(--rgb-yellow)); }
        31.25% { border-right-color: rgb(var(--rgb-lime)); }
        37.5% { border-right-color: rgb(var(--rgb-light-green)); }
        43.75% { border-right-color: rgb(var(--rgb-green)); }
        50% { border-right-color: rgb(var(--rgb-teal)); }
        56.25% { border-right-color: rgb(var(--rgb-cyan)); }
        62.5% { border-right-color: rgb(var(--rgb-light-blue)); }
        68.75% { border-right-color: rgb(var(--rgb-blue)); }
        75% { border-right-color: rgb(var(--rgb-indigo)); }
        81.25% { border-right-color: rgb(var(--rgb-deep-purple)); }
        87.5% { border-right-color: rgb(var(--rgb-purple)); }
        93.75% { border-right-color: rgb(var(--rgb-pink)); }
        100% { border-right-color: rgb(var(--rgb-red)); }
      }
```

### Crescent Spinner

![](https://community-assets.home-assistant.io/original/4X/a/7/9/a79e9ed99fb129a7a809d9ff42fa203bce317148.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Crescent
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        border: 1px solid rgba(var(--rgb-disabled), 0.8);
        border-right: 3px solid rgba(var(--rgb-light-blue));
        --shape-animation: spin 1s linear infinite;
        --shape-color: none;
        --icon-size: 40px;
      }
```

### Munch Spinner

![](https://community-assets.home-assistant.io/original/4X/3/5/6/356b66b8c4b4540679b979610bda4c64ad2eff8d.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Munch
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon, .shape {
        --icon-animation: spin 1.5s linear infinite reverse;
        --shape-animation: spin 2s linear infinite;
        border-radius: 50%;
        border: 4px solid transparent;
        border-right-color: rgb(var(--rgb-amber));
        border-top-color: rgb(var(--rgb-amber));
        --shape-color: none;
        --icon-symbol-size: 34px;
        --icon-size: 34px;
      }
```

### Double Spinner

![](https://community-assets.home-assistant.io/original/4X/7/2/c/72c03bc3eb89a053ab24496e32c236af88ff5615.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Double
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1s linear infinite reverse;
        border-radius: 50%;
        border: 4px double transparent;
        border-right-color: rgb(var(--rgb-deep-orange));
        border-top-color: rgb(var(--rgb-deep-orange));
      }
      .shape {
        border: 4px double transparent;
        border-left-color: rgb(var(--rgb-amber));
        border-bottom-color: rgb(var(--rgb-amber));
        --shape-animation: spin 2s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 20px;
        --icon-size: 34px;
      }
```

### St. Nick Spinner

![](https://community-assets.home-assistant.io/original/4X/5/4/b/54b0c3c96ca878fa54930386531a72b9131b8af7.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: St. Nick
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 0.5s linear infinite reverse;
        border-radius: 50%;
        border: 8px dotted rgb(var(--rgb-red));
      }
      .shape {
        border: 4px dashed rgb(var(--rgb-green));
        --shape-animation: spin 2s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 5px;
        --icon-size: 34px;
      }
```

### Gradient Spinner

![](https://community-assets.home-assistant.io/original/4X/f/6/0/f60ec1d10b29b13793c62a1e367c9ec70e3b06d2.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Gradient
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
         background: radial-gradient(farthest-side, rgb(var(--rgb-blue)) 94%, transparent) top/4px 4px no-repeat, conic-gradient(transparent 30%, rgb(var(--rgb-blue)));
         -webkit-mask: radial-gradient(farthest-side, transparent calc(100% - 4px), #000 0);
         --shape-animation: spin 1s infinite linear;
      }
```

### Dots Spinner

![](https://community-assets.home-assistant.io/original/4X/5/0/b/50b08a1481d3fe3ef03155ec538bfd72cd86442c.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Dots
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
          border: 4px dotted transparent;
          --shape-animation: spin 800ms ease-in-out infinite, color 10s infinite;
          --shape-color: none;
          --icon-size: 34px;
      }
      @keyframes color {
        0% { border-right-color: rgb(var(--rgb-red)); border-top-color: rgb(var(--rgb-red)); }
        6.25% { border-right-color: rgb(var(--rgb-deep-orange)); border-top-color: rgb(var(--rgb-deep-orange)); }
        12.5% { border-right-color: rgb(var(--rgb-orange)); border-top-color: rgb(var(--rgb-orange)); }
        18.75% { border-right-color: rgb(var(--rgb-amber)); border-top-color: rgb(var(--rgb-amber)); }
        25% { border-right-color: rgb(var(--rgb-yellow)); border-top-color: rgb(var(--rgb-yellow)); }
        31.25% { border-right-color: rgb(var(--rgb-lime)); border-top-color: rgb(var(--rgb-lime)); }
        37.5% { border-right-color: rgb(var(--rgb-light-green)); border-top-color: rgb(var(--rgb-light-green)); }
        43.75% { border-right-color: rgb(var(--rgb-green)); border-top-color: rgb(var(--rgb-green)); }
        50% { border-right-color: rgb(var(--rgb-teal)); border-top-color: rgb(var(--rgb-teal)); }
        56.25% { border-right-color: rgb(var(--rgb-cyan)); border-top-color: rgb(var(--rgb-cyan)); }
        62.5% { border-right-color: rgb(var(--rgb-light-blue)); border-top-color: rgb(var(--rgb-light-blue)); }
        68.75% { border-right-color: rgb(var(--rgb-blue)); border-top-color: rgb(var(--rgb-blue)); }
        75% { border-right-color: rgb(var(--rgb-indigo)); border-top-color: rgb(var(--rgb-indigo)); }
        81.25% { border-right-color: rgb(var(--rgb-deep-purple)); border-top-color: rgb(var(--rgb-deep-purple)); }
        87.5% { border-right-color: rgb(var(--rgb-purple)); border-top-color: rgb(var(--rgb-purple)); }
        93.75% { border-right-color: rgb(var(--rgb-pink)); border-top-color: rgb(var(--rgb-pink)); }
        100% { border-right-color: rgb(var(--rgb-red)); border-top-color: rgb(var(--rgb-red)); }
      }
```

### Radial Spinner

![](https://community-assets.home-assistant.io/original/4X/8/a/9/8a90dbf2968b0e2a3df7b1b0e005d5f94d24266f.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Radial
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1.5s linear infinite;
        border-radius: 50%;
        border: 3px solid rgb(var(--rgb-blue));
        border-right-color: transparent;
      }
      .shape {
        border: 3px solid rgb(var(--rgb-red));
        border-right-color: transparent;
        --shape-animation: spin 2s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 24px;
        --icon-size: 36px;
      }
```

### Dual Spinner

![](https://community-assets.home-assistant.io/original/4X/f/c/8/fc8db709406bae447a7bd083b88d3aa4061f0578.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Dual
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        --shape-animation: spin 1s ease infinite;
        border: 4px solid transparent;
        border-top-color: rgb(var(--rgb-deep-orange));
        border-bottom-color: rgb(var(--rgb-deep-orange));
        --shape-color: none !important;
        --icon-size: 34px;
      }
```

### Morse Spinner

![](https://community-assets.home-assistant.io/original/4X/d/a/f/daff425060276caf8d947bcd14f0788dc906153b.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Morse
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1s linear infinite reverse;
        border-radius: 50%;
        border: 4px dashed transparent;
        border-right-color: rgb(var(--rgb-pink));
        border-left-color: rgb(var(--rgb-pink));
      }
      .shape {
        border: 4px dashed transparent;
        border-right-color: rgb(var(--rgb-purple));
        border-left-color: rgb(var(--rgb-purple));
        --shape-animation: spin 2s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 20px;
        --icon-size: 34px;
      }
```

### Fade Spinner

![](https://community-assets.home-assistant.io/original/4X/3/1/5/31546f9636905ab019ea44095700e1e06e2dc39d.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Fade
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        --shape-animation: fade 25s linear infinite reverse;
        --shape-color: none;
      }
      @keyframes fade {
        6.24%, 12.49%, 18.74%, 24.99%, 31.24%, 37.49%, 43.74%, 49.99%, 56.24%, 62.49%, 68.74%, 74.99%, 81.24%, 87.49%, 93.74%, 100%  { box-shadow: 0 0 20px 20px transparent inset; }
        0% { box-shadow: 0 0 0 0 rgba(var(--rgb-red), 0.7) inset; }
        6.25% { box-shadow: 0 0 0 0 rgba(var(--rgb-deep-orange), 0.7) inset; }
        12.5% { box-shadow: 0 0 0 0 rgba(var(--rgb-orange), 0.7) inset; }
        18.75% { box-shadow: 0 0 0 0 rgba(var(--rgb-amber), 0.7) inset; }
        25% { box-shadow: 0 0 0 0 rgba(var(--rgb-yellow), 0.7) inset; }
        31.25% { box-shadow: 0 0 0 0 rgba(var(--rgb-lime), 0.7) inset; }
        37.5% { box-shadow: 0 0 0 0 rgb(var(--rgb-light-green), 0.7) inset; }
        43.75% { box-shadow: 0 0 0 0 rgb(var(--rgb-green), 0.7) inset; }
        50% { box-shadow: 0 0 0 0 rgb(var(--rgb-teal), 0.7) inset; }
        56.25% { box-shadow: 0 0 0 0 rgb(var(--rgb-cyan), 0.7) inset; }
        62.5% { box-shadow: 0 0 0 0 rgb(var(--rgb-light-blue), 0.7) inset; }
        68.75% { box-shadow: 0 0 0 0 rgb(var(--rgb-blue), 0.7) inset; }
        75% { box-shadow: 0 0 0 0 rgb(var(--rgb-indigo), 0.7) inset; }
        81.25% { box-shadow: 0 0 0 0 rgb(var(--rgb-deep-purple), 0.7) inset; }
        87.5% { box-shadow: 0 0 0 0 rgb(var(--rgb-purple), 0.7) inset; }
        93.75% { box-shadow: 0 0 0 0 rgb(var(--rgb-pink), 0.7) inset; }
      }
```

### Dotty Spinner

![](https://community-assets.home-assistant.io/original/4X/0/b/6/0b6d4d0c93b73d7e18961f8f99ab7dc39731d473.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:dots-circle
primary: Dotty
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1s linear infinite reverse, color 60s infinite;
      }
      @keyframes color {
        0% { border-color: rgb(var(--rgb-red)); color: rgb(var(--rgb-red)); }
        6.25% { border-color: rgb(var(--rgb-deep-orange)); color: rgb(var(--rgb-pink)); }
        12.5% { border-color: rgb(var(--rgb-orange)); color: rgb(var(--rgb-purple)); }
        18.75% { border-color: rgb(var(--rgb-amber)); color: rgb(var(--rgb-deep-purple)); }
        25% { border-color: rgb(var(--rgb-yellow)); color: rgb(var(--rgb-indigo)); }
        31.25% { border-color: rgb(var(--rgb-lime)); color: rgb(var(--rgb-blue)); }
        37.5% { border-color: rgb(var(--rgb-light-green)); color: rgb(var(--rgb-light-blue)); }
        43.75% { border-color: rgb(var(--rgb-green)); color: rgb(var(--rgb-cyan)); }
        50% { border-color: rgb(var(--rgb-teal)); color: rgb(var(--rgb-teal)); }
        56.25% { border-color: rgb(var(--rgb-cyan)); color: rgb(var(--rgb-green)); }
        62.5% { border-color: rgb(var(--rgb-light-blue)); color: rgb(var(--rgb-light-green)); }
        68.75% { border-color: rgb(var(--rgb-blue)); color: rgb(var(--rgb-lime)); }
        75% { border-color: rgb(var(--rgb-indigo)); color: rgb(var(--rgb-yellow)); }
        81.25% { border-color: rgb(var(--rgb-deep-purple)); color: rgb(var(--rgb-amber)); }
        87.5% { border-color: rgb(var(--rgb-purple)); color: rgb(var(--rgb-orange)); }
        93.75% { border-color: rgb(var(--rgb-pink)); color: rgb(var(--rgb-deep-orange)); }
        100% { border-color: rgb(var(--rgb-red)); color: rgb(var(--rgb-red)); }
      }
      .shape {
        --shape-color: none;
        border: 5px dotted transparent;
        --shape-animation: spin 2s linear infinite, color 60s infinite;
        --icon-symbol-size: 30px;
        --icon-size: 32px;
      }
```

### Plain Spinner

![](https://community-assets.home-assistant.io/original/4X/c/9/1/c91c60bf7291956cf8d8111ef937e1b30b224adb.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Plain
card_mod:
  style:
    mushroom-shape-icon$: |
      .shape {
        border: 5px solid rgb(var(--rgb-disabled));
        border-left-color: transparent;
        --shape-animation: spin 1s linear infinite;
        --shape-color: none;
        --icon-size: 32px;
      }
```

### Toggle Spinner

![](https://community-assets.home-assistant.io/original/4X/b/4/2/b4200accf7236a3fa3e4d5e2637d7679fdf3f7f2.gif)

```yaml
type: custom:mushroom-template-card
icon: none
primary: Toggle
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1s linear infinite reverse;
        border-radius: 50%;
        border: 4px solid transparent;
        border-right-color: rgb(var(--rgb-cyan));
        border-left-color: rgb(var(--rgb-cyan));
      }
      .shape {
        border: 4px solid transparent;
        border-top-color: rgb(var(--rgb-cyan));
        border-left-color: rgb(var(--rgb-cyan));
        --shape-animation: spin 1s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 34px;
        --icon-size: 34px;
      }
```

### Spheres Spinner

![](https://community-assets.home-assistant.io/original/4X/3/3/7/337e435f3fd57ac066384d43d81430f279ea3185.gif)

```yaml

type: custom:mushroom-template-card
icon: none
primary: Spheres
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 1s linear infinite reverse;
        border-radius: 50%;
        border: 12px dotted transparent;
        border-right-color: rgb(var(--rgb-blue));
        border-left-color: rgb(var(--rgb-blue));
      }
      .shape  {
        border: 12px dotted transparent;
        border-right-color: rgb(var(--rgb-red));
        border-left-color: rgb(var(--rgb-red));
        --shape-animation: spin 2s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 18px;
        --icon-size: 18px;
      }
```

### Triple Spinner

![](https://community-assets.home-assistant.io/original/4X/b/6/5/b651709838934de52191981d6998400fe6e50270.gif)

```yaml
type: custom:mushroom-template-card
icon: mdi:loading
icon_color: red
primary: Triple
card_mod:
  style:
    mushroom-shape-icon$: |
      ha-icon {
        --icon-animation: spin 4s linear infinite;
        border-radius: 50%;
        border: 4px solid transparent;
        border-bottom-color: rgb(var(--rgb-blue));
      }
      .shape {
        --shape-color: none !important;
        border: 4px solid transparent;
        border-bottom-color: rgb(var(--rgb-green));
        --shape-animation: spin 2s linear infinite;
        --shape-color: none;
        --icon-symbol-size: 42px;
        --icon-size: 34px;
      }
```

## Mushroom Card Active Animations

### Activate Background

![](https://community-assets.home-assistant.io/original/4X/e/0/0/e00a3d804ec42926a5ad28313834c34f286ca1b9.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Background
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active {
      background: rgba(var(--rgb-disabled), 0.1);
      transition: 0s;
    }
```

### Activate Box-Shadow

![](https://community-assets.home-assistant.io/original/4X/5/e/9/5e9be9640ae2125a88c2892342c346166ef1fe59.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Box-Shadow
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active {
      box-shadow: 0 0 20px rgba(var(--rgb-disabled), 0.8);
      transition: 0s;
    }
```

### Activate Scale-Out

![](https://community-assets.home-assistant.io/original/4X/e/3/1/e313e0eac0bcae6f9a021ecf6d04473cf3031005.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Scale-Out
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active {
      transform: scale(1.02);
      transition: 0s;
    }
```

### Activate Scale-In

![](https://community-assets.home-assistant.io/original/4X/3/a/0/3a040597fce00c5c3d8a0bd1d549e22ef53da42e.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Scale-In
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active {
      transform: scale(0.975);
      transition: 0s;
    }

```

### Activate Push Down

![](https://community-assets.home-assistant.io/original/4X/7/e/b/7eb8b057df6586083a1b6eb753256a423bf63545.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Push Down
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active {
      transform: translateY(1.5px);
      transition: 0s;
      box-shadow: 0 0.5px 2px 0 rgba(0, 0, 0, 0.16);
    }
```

### Activate Push In

![](https://community-assets.home-assistant.io/original/4X/a/b/d/abd279d1cf8d4fc22a393d7091f5cc1ce40533be.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Push In
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active {
      transform: translateY(-1.5px);
      transition: 0s;
      box-shadow: 0 0.5px 2px 0 rgba(0, 0, 0, 0.16);
    }
```

### Activate Ripple

![](https://community-assets.home-assistant.io/original/4X/0/c/d/0cd0b4748e716ad02cbc75de5b28d7572d1507bc.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Ripple
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card {
      overflow: hidden;
    }  
    ha-card:after {
      display: none;
      content: "";
      position: absolute;
      border-radius: 50%;
      background-color: rgba(var(--rgb-disabled), 0.1);
      width: 100px;
      height: 100px;
      margin-top: -50px;
      margin-left: -50px;
      top: 50%;
      left: 50%;
      animation: ripple 750ms;
      opacity: 0;
    }
    ha-card:active:after {
      display: block;
    }
    @keyframes ripple {
      from { opacity: 1; transform: scale(0); }
      to { opacity: 0; transform: scale(10); }
    }
```

### Activate 3D Perspective

![](https://community-assets.home-assistant.io/original/4X/2/5/e/25ed9038bb1c9073d1420f4d3d6cc572cc8c10e9.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: 3D Perspective
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    :host {
      perspective: 900px;
    }
    ha-card:active {
      transform: rotateY(20deg);
      transition: 0s;
    }
```

### Activate 3D Tilt

![](https://community-assets.home-assistant.io/original/4X/6/2/1/621d904e1fb0a9284c9a863776487eb6eedc2eb0.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: 3D Tilt
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    :host {
      perspective: 1000px;
    }
    ha-card:active {
      transform: rotate3d(0.5, -0.9, 0, 10deg) rotate(1deg);
      transition: 0s;
    }
```

### Activate 3D Flap

![](https://community-assets.home-assistant.io/original/4X/7/b/4/7b43b0b32d75bec51024a658460187dfac43ea38.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: 3D Flap
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    :host {
      perspective: 900px;
    }
    ha-card:active {
      transform: rotateX(25deg);
      transform-origin: center bottom;
      transition: 0s;
    }

```

### Activate Icon Spin

![](https://community-assets.home-assistant.io/original/4X/b/c/9/bc99d523341f5fc2a7b9ec28a5a5975171d54816.gif)

```yaml
type: custom:mushroom-template-card
primary: Activate Mushroom
icon: mdi:mushroom
icon_color: red
secondary: Icon Spin
tap_action:
  action: none
hold_action:
  action: none
card_mod:
  style: |
    ha-card:active mushroom-shape-icon { 
        display: flex;
        #--icon-animation: spin 1s;
        transform: rotate(360deg);
        transition: 500ms;
    }
Applying Active Animations to your Theme

Rather than applying the active animations to each card, you can apply the to all cards by adding the card_mod to your theme.

Mushroom Custom:
  card-mod-theme: "Mushroom Custom"

  card-mod-card: |
    ha-card:active {
      transform: scale(1.02);
      transition: 0s;
    }
```
