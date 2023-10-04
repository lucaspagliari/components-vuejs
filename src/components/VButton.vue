<script setup>

defineProps({
  color: {
    type: String,
    default: '#646cff'
  },
})


</script>

<template>
  <button>
    <slot name="default"></slot>
  </button>
</template>

<style scoped>
button {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.80em 1.2em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  background-color: v-bind(color);
  cursor: pointer;
  border-width: 2px;
  transition: border-color 0.25s;
}

button:hover {
  border-color: #d8d8d8;
}
button:focus,
button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;
}
</style>
