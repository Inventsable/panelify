# panelify [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[![NPM](https://nodei.co/npm/@inventsable/panelify.png)](https://nodei.co/npm/@inventsable/panelify/)

Custom Vue component compatible with [generator-cep-vue-cli extensions](https://github.com/Inventsable/generator-cep-vue-cli) to display Adobe panel mocks inside your browser, allowing users to play with a mock version of your UI in good faith as a _Try Before You Buy_ policy.

## [See 4 demo panels in the same page](https://inventsable-panels.web.app)

![](https://thumbs.gfycat.com/ShortDismalCicada-size_restricted.gif)

## Installation

```bash
npm install @inventsable/panelify
```

## Usage

> Will do write up on how to achieve full result soon

```html
<template>
  <panelify
    extName="camAssist"
    appName="AEFT"
    src="https://camera-manager-panel.web.app/#/"
    width="450px"
    height="300px"
    :gradient="0"
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
