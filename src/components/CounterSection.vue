<template>
  <section>
    <h2>Counter Section</h2>
    <button @click="count++">Clicked {{ count }} times</button>
  </section>
</template>

<script setup>
import { ref } from "vue";
const count = ref(0);
</script>

<style scoped>
section {
  background: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
  border-radius: 1.5rem;
  box-shadow: 0 4px 24px 0 rgba(246, 211, 101, 0.18);
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
button {
  background: #fda085;
  color: #fff;
  border: none;
  font-weight: 700;
  font-size: 1.1rem;
  border-radius: 0.7rem;
  padding: 0.7rem 1.5rem;
  margin-top: 1.2rem;
  cursor: pointer;
  box-shadow: 0 2px 8px rgba(246, 211, 101, 0.12);
  transition: background 0.2s;
}
button:hover {
  background: #f6d365;
}
</style>
