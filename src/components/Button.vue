<template>
  <button type="submit" class="button">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: {
      type: String,
      required: true
    }
  }
};
</script>
