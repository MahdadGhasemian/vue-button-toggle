<script>
import Vue from 'vue';
import VueButtonToggle from '@/vue-button-toggle.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueButtonToggle
  }
});
</script>

<template>
  <div id="app">
    <vue-button-toggle />
  </div>
</template>
