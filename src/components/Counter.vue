<script setup>
import { ref } from "vue";

const count = ref(0);
</script>

<template>
  <h1>Counter</h1>
  <h4>{{ count }}</h4>
  <button @click="count--">-</button>
  <button @click="count++">+</button>
</template>
