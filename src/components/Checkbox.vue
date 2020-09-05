<template>
  <label class="checkbox-container-wrapper">
    <label class="checkbox-container">
      <input type="checkbox" class="checkbox-input" />
      <span class="checkmark" />
    </label>
    <span class="checkbox-label">{{ label }}</span>
  </label>
</template>

<script>
export default {
  name: "Checkbox",
  props: {
    label: {
      type: [String, Number],
      required: true
    }
  }
};
</script>
