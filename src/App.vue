<script setup>
import VButton from "./components/VButton.vue";
import VTypography from "./components/VTypography.vue";
import VCard from "./components/VCard.vue";
import VTextField from "./components/VTextField.vue";

import { ref } from "vue";

const name = ref("");
</script>

<template>
  <div>
    <VTypography type="title" color="#fff9f9">
      INF331 - Web Components in Vue.js
    </VTypography>
  </div>

  <div class="container-column">
    <VTypography type="subtitle" color="#ff9a9a">
      Componente de Botão
    </VTypography>
    
    <div class="container">
      <VButton>Botão</VButton>
      <VButton color="#9099ef">Botão</VButton>
      <VButton color="#6499ff">Botão</VButton>
      <VButton color="#3099ff">Botão</VButton>
    </div>
  </div>

  <br />

  <div class="container container-column">
    <VTypography type="subtitle" color="#ff9a9a">
      Componente de Tipografia
    </VTypography>

    <VTypography type="title">Título</VTypography>
    <VTypography type="subtitle">Sub título</VTypography>
    <VTypography>Texto</VTypography>
  </div>
  <br />

  <div class="container container-column">
    <VTypography type="subtitle" color="#ff9a9a">
      Componente de Cartão
    </VTypography>
    <VCard>
      <template #title>Título card</template>
      <template #default> Corpo de card </template>
      <template #action> Ações </template>
    </VCard>

    <br />
    <VTypography type="subtitle" color="#ff9a9a">
      Composição de componentes
    </VTypography>

    <VCard>
      <template #title>
        <VTypography type="subtitle">Dados do usuário</VTypography>
      </template>

      <template #default>
        <VTextField
          v-model="name"
          label="Nome do usuário"
          placeholder="Digite o nome de usuário"
        />

        <VTypography>{{ name || "-" }} </VTypography>
      </template>

      <template #action>
        <VButton color="#3099ff">Confirmar</VButton>
        <VButton color="#d11041">Cancelar</VButton>
      </template>
    </VCard>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.container-column {
  flex-direction: column;
  gap: 1rem;
}
</style>
