<script setup>
import { onMounted, ref } from "vue";

const emit = defineEmits(["update:modelValue"]);

defineProps({
  modelValue: {
    type: String,
  },
  label: {
    type: String,
  },
  placeholder: {
    type: String,
  },
});

const name = ref("");
onMounted(() => {
  name.value = Date.now().toString(16);
});
</script>

<template>
  <div class="v-text-field">
    <label v-if="label" :for="name">{{ label }}</label>
    <input
      :name="name"
      :placeholder="placeholder"
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>

<style scoped>
.v-text-field {
  display: flex;
  flex-direction: column;
}
label {
  font-size: 18px;
  font-weight: 500;
  text-align: start;
}
input {
  width: 100%;
  border-radius: 8px;
  border: 2px solid #535353;
  padding: 0.8em 0.5rem;
  font-size: 1em;
  font-weight: 600;
  background-color: transparent;
  color: inherit;
  box-sizing: border-box;
}
</style>
