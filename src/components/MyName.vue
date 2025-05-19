<script setup>
import { ref } from 'vue'

const name = ref('')
</script>

<template>
  <div class="name-display">
    <h1>Entrez votre prénom :</h1>
    <input v-model="name" type="text" placeholder="Votre prénom" />

    <p v-if="name">Bonjour, {{ name }} !</p>
    <p v-else>Veuillez entrer votre prénom</p>
  </div>
</template>

<style scoped>
.name-display {
  text-align: center;
  margin-top: 50px;
  font-family: sans-serif;
}

input {
  padding: 8px 12px;
  font-size: 16px;
}
</style>
