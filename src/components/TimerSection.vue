<template>
  <section>
    <h2>Timer Section</h2>
    <div class="timer">Timer: {{ seconds }}s</div>
    <div class="timer-btns">
      <button @click="start">Start</button>
      <button @click="stop">Stop</button>
      <button @click="reset">Reset</button>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
let interval = null;
const seconds = ref(0);
function start() {
  if (!interval) {
    interval = setInterval(() => seconds.value++, 1000);
  }
}
function stop() {
  clearInterval(interval);
  interval = null;
}
function reset() {
  stop();
  seconds.value = 0;
}
</script>

<style scoped>
section {
  background: linear-gradient(120deg, #f7971e 0%, #ffd200 100%);
  border-radius: 1.5rem;
  box-shadow: 0 4px 24px 0 rgba(255, 210, 0, 0.18);
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
.timer {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 1.2rem;
  color: #f7971e;
}
.timer-btns {
  display: flex;
  gap: 1rem;
}
button {
  background: #ffd200;
  color: #2a3142;
  border: none;
  font-weight: 700;
  font-size: 1.1rem;
  border-radius: 0.7rem;
  padding: 0.7rem 1.5rem;
  margin-top: 1.2rem;
  cursor: pointer;
  box-shadow: 0 2px 8px rgba(255, 210, 0, 0.12);
  transition: background 0.2s;
}
button:hover {
  background: #f7971e;
  color: #fff;
}
</style>
