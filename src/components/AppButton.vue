<template>
  <button
    :class="{
      'border rounded p-5 py-2 disabled:cursor-not-allowed disabled:bg-red-300': true,
      'bg-blue-300 hover:bg-blue-500': type === 'primary',
      'bg-green-300 hover:bg-green-500': type === 'secondary',
      'bg-red-300 hover:bg-red-500': type === 'danger',
      'bg-yellow-300 hover:bg-yellow-500': type === 'warning',
      'is-loading': processing,
    }"
    :disabled="processing"
  >
    <slot />
  </button>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: "primary",
    },
    processing: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
