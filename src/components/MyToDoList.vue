<script setup>
import { ref } from 'vue'

const newTask = ref('')
const tasks = ref([])

function addTask() {
  const trimmed = newTask.value.trim()
  if (trimmed) {
    tasks.value.push(trimmed)
    newTask.value = ''
  }
}

function removeTask(index) {
  tasks.value.splice(index, 1)
}
</script>

<template>
  <div>
    <h1>Ma To-Do List</h1>

    <input v-model="newTask" placeholder="Nouvelle tâche" />
    <button @click="addTask">Ajouter</button>

    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <button @click="removeTask(index)">Supprimer</button>
      </li>
    </ul>

    <p v-if="tasks.length === 0">Aucune tâche pour le moment.</p>
  </div>
</template>

<style scoped>
input {
  padding: 8px;
  margin-right: 8px;
}

button {
  padding: 6px 12px;
  margin-left: 4px;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
}

li {
  margin: 10px 0;
}
</style>
