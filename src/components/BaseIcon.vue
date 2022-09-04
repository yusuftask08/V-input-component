<template>
  <component :is="iconComponent" />
</template>

<script>
const icons = {
  info: require("./Icons/InfoIcon.vue").default,
  close: require("./Icons/CloseIcon.vue").default,
};
export default {
  props: {
    name: {
      type: String,
      required: true,
      validator(value) {
        return Object.prototype.hasOwnProperty.call(icons, value);
      },
    },
  },
  computed: {
    iconComponent() {
      return icons[this.name];
    },
  },
};
</script>

<style>
</style>