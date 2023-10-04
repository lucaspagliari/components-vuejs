<script setup></script>

<template>
  <div class="v-card">
    <div class="v-card-title">
      <slot name="title"></slot>
    </div>

    <slot name="default"></slot>

    <div class="v-card-actions">
      <slot name="action"></slot>
    </div>
  </div>
</template>

<style scoped>
.v-card {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;

  border-radius: 8px;
  padding: 1.2rem 1.4rem;
  background-color: rgb(231, 231, 231);
  color: #2a2a2c;
}

.v-card-title {
  text-align: left;
  margin-bottom: 0.5rem;
  font-size: 32px;
}
.v-card-actions {
  display: flex;
  justify-content: space-between;
}
</style>
