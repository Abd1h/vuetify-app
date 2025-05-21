<template>
  <section>
    <h2>Color Picker Section</h2>
    <input type="color" v-model="color" />
    <span :style="{ color }" class="color-label"
      >Selected Color: {{ color }}</span
    >
  </section>
</template>

<script setup>
import { ref } from "vue";
const color = ref("#ff0000");
</script>

<style scoped>
section {
  background: linear-gradient(120deg, #fbc2eb 0%, #a6c1ee 100%);
  border-radius: 1.5rem;
  box-shadow: 0 4px 24px 0 rgba(251, 194, 235, 0.18);
  padding: 2.5rem 3rem;
  min-width: 320px;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 1rem auto;
}
h2 {
  color: #111;
  font-weight: 900;
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
}
input[type="color"] {
  width: 60px;
  height: 40px;
  border: none;
  margin: 1rem 0;
  background: none;
  cursor: pointer;
  border-radius: 0.7rem;
  box-shadow: 0 2px 8px rgba(166, 193, 238, 0.12);
}
.color-label {
  font-size: 1.1rem;
  font-weight: 500;
  margin-top: 0.5rem;
}
</style>
