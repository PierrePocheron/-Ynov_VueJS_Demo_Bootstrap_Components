<template>
  <button
    type="button"
    class="btn"
    :class="[`btn-${theme}`, size && `btn-${size}`, { 'd-block w-100': block }]"
    :disabled="disabled"
  >
    <div>loading</div>
    <slot />
  </button>
</template>

<script>
export default {
  props: {
    theme: {
      type: String,
      required: false,
      default: "primary",
      validator: (value) => {
        return [
          "primary",
          "secondary",
          "success",
          "danger",
          "warning",
          "info",
          "light",
          "dark",
        ].includes(value);
      },
    },
    size: {
      type: String,
      required: false,
      default: "md",
      validator: (value) => {
        return [
          "sm",
          "md",
          "lg",
          "xl",
          "2xl",
          "3xl",
          "4xl",
          "5xl",
          "6xl",
          "7xl",
        ];
      },
    },
    disabled: {
      type: Boolean,
      required: false,
    },
    loading: {
      type: Boolean,
      required: false,
    },
  },
};
</script>
