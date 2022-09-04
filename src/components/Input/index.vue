<template>
  <div>
    <span v-if="label" class="input-label"> {{ label }} </span>
    <div class="input-container" :class="classSize">
      <input
        :type="type"
        class="input"
        :class="classList"
        :placeholder="placeholder"
        :disabled="disabled"
        :value="modelValue"
        @input="inputValue"
        @focus="$emit('focus')"
        v-bind="$attrs"
      />
      <div class="right-icon">
        <span
          v-if="modelValue.length > 0"
          class="clear-icon"
          @click="$emit('input', (modelValue = ''))"
        >
          <BaseIcon name="close" />
        </span>
      </div>
    </div>
    <div class="helper-container">
      <span class="helper-text">
        {{ helper }}
        <BaseIcon v-if="helperIcon" :name="helperIcon" width="20" height="15" />
      </span>
    </div>
  </div>
</template>

<script>
import BaseIcon from "@/components/BaseIcon.vue";
export default {
  name: "GInput",
  components: {
    BaseIcon,
  },
  props: {
    placeholder: {
      type: String,
      default: "placeholder",
    },
    label: {
      type: String,
    },
    helper: {
      type: String,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    icon: {
      type: String,
    },
    size: {
      type: String,
      default: "small",
      in: ["small", "medium", "large"],
    },
    helperIcon: {
      type: String,
    },
    type: {
      type: String,
      default: "text",
    },
  },
  data() {
    return {
      modelValue: "",
    };
  },
  methods: {
    inputValue(event) {
      this.$emit("inputValue", (this.modelValue = event.target.value));
    },
  },

  computed: {
    classList() {
      const vm = this;
      return {
        ["disabled"]: vm.disabled,
        ["icon"]: vm.icon,
      };
    },
    classSize() {
      const vm = this;
      return {
        [`input-${vm.size}`]: vm.size,
      };
    },
  },
};
</script>

<style lang="scss">
@import "../../style/input.scss";
</style>