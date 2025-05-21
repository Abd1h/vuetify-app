<template>
  <section>
    <h2>Todo List Section</h2>
    <input
      v-model="newTodo"
      @keyup.enter="addTodo"
      placeholder="Add a todo"
      type="text"
    />
    <ul class="todo-list">
      <li v-for="(todo, idx) in todos" :key="idx">
        <input type="checkbox" v-model="todo.done" />
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
      </li>
    </ul>
  </section>
</template>

<script setup>
import { ref } from "vue";
const newTodo = ref("");
const todos = ref([]);
function addTodo() {
  if (newTodo.value.trim()) {
    todos.value.push({ text: newTodo.value, done: false });
    newTodo.value = "";
  }
}
</script>

<style scoped>
section {
  background: linear-gradient(120deg, #d4fc79 0%, #96e6a1 100%);
  border-radius: 1.5rem;
  box-shadow: 0 4px 24px 0 rgba(150, 230, 161, 0.18);
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
input[type="text"] {
  width: 220px;
  margin-bottom: 1rem;
  border-radius: 0.7rem;
  border: 1px solid #b7e4c7;
  padding: 0.5rem 1rem;
  font-size: 1rem;
}
.todo-list {
  list-style: none;
  padding: 0;
  width: 100%;
}
.todo-list li {
  display: flex;
  align-items: center;
  margin-bottom: 0.5rem;
}
.todo-list input[type="checkbox"] {
  margin-right: 0.7rem;
}
.done {
  text-decoration: line-through;
  color: #9ca3af;
}
</style>
