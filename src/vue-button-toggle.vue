<script>
export default {
  name: "VueButtonToggle",
  props: {
    value: {
      type: Boolean,
      default: false,
    },
    bgActiveColor: {
      type: String,
      default: "#FFFFFF",
    },
    bgDeactiveColor: {
      type: String,
      default: "#000000",
    },
    dotActiveColor: {
      type: String,
      default: "#000000",
    },
    dotDeactiveColor: {
      type: String,
      default: "#FFFFFF",
    },
  },
  data() {
    return {
      checked: false,
    };
  },
  computed: {
    cssProps() {
      return {
        "--bg-active-color": this.bgActiveColor,
        "--bg-deactive-color": this.bgDeactiveColor,
        "--dot-active-color": this.dotActiveColor,
        "--dot-deactive-color": this.dotDeactiveColor,
      };
    },
  },
  watch: {
    checked() {
      this.$emit("input", this.checked);
    },
    value() {
      this.checked = this.value;
    },
  },
  created() {
    this.checked = this.value;
  },
};
</script>

<template>
  <label class="main-box" :style="cssProps">
    <!-- label -->
    <slot name="before"></slot>
    <!-- toggle -->
    <div class="toggle-box">
      <!-- input -->
      <input v-model="checked" type="checkbox" class="input" />
      <!-- line -->
      <div class="line"></div>
      <!-- dot -->
      <div class="dot"></div>
    </div>
    <!-- label -->
    <slot name="after"></slot>
  </label>
</template>

<style scoped>
.main-box {
  padding: 0;
  margin: 0;
  list-style: none;
  display: flex;
  justify-content: center;
  -webkit-align-items: center;
  align-items: center;
  cursor: pointer;
}

.input {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}

.toggle-box {
  position: relative;
}
.line {
  display: block;
  width: 3.5rem;
  height: 2rem;
  border-radius: 9999px;
}

input:checked ~ .dot {
  transform: translateX(100%);
  background-color: var(--dot-active-color);
}
.dot {
  background-color: var(--dot-deactive-color);
  position: absolute;
  left: 0.25rem;
  top: 0.25rem;
  background-color: white;
  width: 1.5rem;
  height: 1.5rem;
  border-radius: 9999px;
  transition-property: background-color, border-color, color, fill, stroke,
    opacity, box-shadow, transform, filter, backdrop-filter;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}
input:checked ~ .line {
  background-color: var(--bg-active-color);
}
.line {
  background-color: var(--bg-deactive-color);
}
</style>
