<script setup>
import { ref } from "vue";

const count = ref(0);
</script>

<template>
  <div class="wrapper">
    <h1>Counter</h1>
    <h4>{{ count }}</h4>
    <div>
      <button @click="count--">-</button>
      <button @click="count++">+</button>
    </div>
  </div>
</template>

<style scoped>
button:hover {
  cursor: pointer;
}
.wrapper {
  display: grid;
  place-items: center;
}
</style>
