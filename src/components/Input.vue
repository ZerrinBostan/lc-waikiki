<template>
  <div class="input-wrapper">
    <i :class="'icon-login ' + icon"></i>
    <input class="input" :type="input_type" :placeholder="placeholder" />
  </div>
</template>

<script>
export default {
  name: "Input",
  props: {
    placeholder: {
      type: String,
      default: ""
    },
    icon: {
      type: String,
      default: ""
    },
    input_type: {
      type: String,
      default: "text"
    }
  }
};
</script>
