<template>
  <section>
    <h2>Random Joke Section</h2>
    <button @click="getJoke">Get Random Joke</button>
    <p v-if="joke" class="joke">{{ joke }}</p>
  </section>
</template>

<script setup>
import { ref } from "vue";
const joke = ref("");
function getJoke() {
  const jokes = [
    "Why did the scarecrow win an award? Because he was outstanding in his field!",
    "Why don’t skeletons fight each other? They don’t have the guts.",
    "What do you call fake spaghetti? An impasta!",
    "Why did the math book look sad? Because it had too many problems.",
  ];
  joke.value = jokes[Math.floor(Math.random() * jokes.length)];
}
</script>

<style scoped>
section {
  background: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
  border-radius: 1.5rem;
  box-shadow: 0 4px 24px 0 rgba(161, 196, 253, 0.18);
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
  background: #5398ff;
  color: #fff;
  border: none;
  font-weight: 700;
  font-size: 1.1rem;
  border-radius: 0.7rem;
  padding: 0.7rem 1.5rem;
  margin-top: 1.2rem;
  cursor: pointer;
  box-shadow: 0 2px 8px rgba(161, 196, 253, 0.12);
  transition: background 0.2s;
}
button:hover {
  background: #a1c4fd;
}
.joke {
  margin-top: 1.2rem;
  font-size: 1.1rem;
  color: #374151;
  text-align: center;
}
</style>
