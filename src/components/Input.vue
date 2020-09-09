<template>
  <div :class="['input-wrapper', !!error && 'input-wrapper-error']">
    <i :class="'icon-login ' + icon"></i>
    <input
      :name="name"
      class="input"
      :type="type"
      :placeholder="placeholder"
      @input="callback"
      @blur="$emit('validate')"
      @keypress="$emit('validate')"
    />
  </div>
  <span class="text-error" v-if="!!error">{{ error }}</span>
</template>

<script>
export default {
  name: "Input",
  props: {
    icon: {
      type: String,
      default: ""
    },
    name: {
      type: String,
      required: true
    },
    error: {
      type: String,
      required: true
    },
    type: {
      type: String,
      default: "text"
    },
    placeholder: {
      type: String,
      default: ""
    },
    callback: Function
  }
};
</script>
