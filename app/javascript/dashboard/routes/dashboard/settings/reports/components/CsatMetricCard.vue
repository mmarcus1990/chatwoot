<template>
  <div
    class="medium-2 small-6 csat--metric-card"
    :class="{
      disabled: disabled,
    }"
  >
    <h3 class="heading">
      <span>{{ label }}</span>
      <fluent-icon
        v-tooltip="infoText"
        size="14"
        icon="info"
        class="csat--icon"
      />
    </h3>
    <h4 class="metric">
      {{ value }}
    </h4>
  </div>
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
    infoText: {
      type: String,
      required: true,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
<style lang="scss" scoped>
.csat--metric-card {
  margin: 0;
  padding: var(--space-normal);

  &.disabled {
    // grayscale everything
    filter: grayscale(100%);
    opacity: 0.3;
    pointer-events: none;
  }

  .heading {
    align-items: center;
    color: var(--color-heading);
    display: flex;
    font-size: var(--font-size-small);
    font-weight: var(--font-weight-bold);
    margin: 0;
  }

  .metric {
    font-size: var(--font-size-bigger);
    font-weight: var(--font-weight-feather);
    margin-bottom: 0;
    margin-top: var(--space-smaller);
  }
}

.csat--icon {
  color: var(--b-400);
  margin: 0 var(--space-micro);
}
</style>
