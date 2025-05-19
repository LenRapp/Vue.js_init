<script setup>
  import {ref} from "vue";
  const count = ref(0);
  function increment() {
    count.value++;
  }

  function decrement() {
    if (count.value > 0) {
      count.value--;
    }
  }
</script>

<template>
  <div class="counter">
    <h2>Counter : {{ count }}</h2>

    <button @click="increment">+1</button>
    <button @click="decrement" :disabled="count ===0">-1</button>

    <p v-if="count > 10">Tu as dépassé 10</p>
  </div>
</template>

<style scoped>
.counter {
  text-align: center;
  margin-top: 50px;
  font-family: sans-serif;
}

.value {
  font-size: 36px;
  margin: 20px 0;
}

button {
  padding: 8px 16px;
  font-size: 16px;
  margin: 0 10px;
}
</style>
