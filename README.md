# panelify

## 🔨 Under Construction 🔨

Custom Vue component to display Adobe panel mocks inside your browser, allow users to play with a mock version of your UI in good faith as a _Try Before You Buy_ policy.

## [See a demo After Effects panel](https://inventsable-panels.web.app/camAssist)

![](https://thumbs.gfycat.com/ShortDismalCicada-size_restricted.gif)

## Intended Installation

```bash
npm install @inventsable/panelify
```

## Intended Usage

> Will do write up on iframe contents later

```html
<template>
  <panelify
    extName="camAssist"
    appName="AEFT"
    src="https://camera-manager-panel.web.app/#/"
  />
</template>

<script>
  // Must explicitly import the panelify element (and conversely import the shim in your iframe environment)
  import { panelify } from "@/components/panelify";

  export default {
    name: "home",
    components: {
      panelify
    }
  };
</script>
```
