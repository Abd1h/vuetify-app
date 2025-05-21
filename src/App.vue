<template>
  <VRow class="main-sections" align="center" justify="center" no-gutters>
    <VCol cols="12" v-for="(Comp, idx) in sections" :key="idx">
      <section class="section-card">
        <component :is="Comp" />
      </section>
    </VCol>
  </VRow>
</template>

<script setup>
import CounterSection from "./components/CounterSection.vue";
import RandomJokeSection from "./components/RandomJokeSection.vue";
import ColorPickerSection from "./components/ColorPickerSection.vue";
import TodoListSection from "./components/TodoListSection.vue";
import TimerSection from "./components/TimerSection.vue";

const sections = [
  CounterSection,
  RandomJokeSection,
  ColorPickerSection,
  TodoListSection,
  TimerSection,
];
</script>

<style scoped></style>
