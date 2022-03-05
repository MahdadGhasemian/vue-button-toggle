# Vue Button Toggle Component

A Customizable Toggle/Switch Button Component For Vue

## Installation

### npm

```bash
npm i vue-button-toggle --save
```

### Usage

main.js

```javascript
//...
import VueButtonToggle from "vue-button-toggle";
Vue.component("vue-button-toggle", VueButtonToggle);
//...
```

Or in component

```html
<template>
  <div>
    <vue-button-toggle
      v-model="wifiSwitch"
      bg-active-color="#0071FF"
      bg-deactive-color="#787880"
      dot-active-color="#FFFFFF"
      dot-deactive-color="#FFFFFF"
    >
    </vue-button-toggle>
  </div>
</template>

<script>
  import VueButtonToggle from "vue-button-toggle";
  export default {
    components: {
      VueButtonToggle: VueButtonToggle,
    },
  };
</script>
```

## Nuxt [nuxtjs](https://nuxtjs.org/)

### npm

```bash
npm i vue-button-toggle --save
```

### Config as plugin

/plugins/vue-button-toggle.js :

```javascript
import Vue from "vue";
import VueButtonToggle from "vue-button-toggle";

Vue.component("vue-button-toggle", VueButtonToggle);
```

/nuxt.config.js

```javascript
plugins: ['~/plugins/vue-button-toggle.js'],
```

### Usage

```html
<template>
  <div>
    <vue-button-toggle
      v-model="wifiSwitch"
      bg-active-color="#0071FF"
      bg-deactive-color="#787880"
      dot-active-color="#FFFFFF"
      dot-deactive-color="#FFFFFF"
    >
    </vue-button-toggle>
  </div>
</template>
```

## Examples

### Example1

```html
<template>
  <div>
    <vue-button-toggle
      v-model="switchValue"
      bg-active-color="#0071FF"
      bg-deactive-color="#787880"
      dot-active-color="#FFFFFF"
      dot-deactive-color="#FFFFFF"
    >
      <template #before>
        <div style="margin-right: 15px;">Before!</div>
      </template>
      <template #after>
        <div style="margin-left: 15px;">After!</div>
      </template>
    </vue-button-toggle>
  </div>
</template>
```

## Change log

### 0.0.1 (2022-03-05)

- first release

<br />
<br />
<br />
<hr />
