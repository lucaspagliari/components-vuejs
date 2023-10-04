<script setup>
defineProps({
  type: {
    type: String,
    default: "text",
  },
  color: {
    type: String,
  },
});
</script>

<template>
  <span :class="['v-typography', `v-typography-${type}`]">
    <slot name="default"></slot>
  </span>
</template>

<style scoped>
.v-typography {
  color: v-bind(color);
}

.v-typography-title {
  font-size: 32px;
  font-weight: 700;
  line-height: 42px;
}
.v-typography-subtitle {
  font-size: 24px;
  font-weight: 700;
  line-height: 32px;
}

.v-typography-text {
  font-size: 18px;
  font-weight: 500;
  line-height: 24px;
}
</style>
