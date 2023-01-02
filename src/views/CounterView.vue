<script setup>
import Counter from "../components/Counter.vue";
</script>

<template>
  <div class="about">
    <div>
      <h1>This is the Counter page</h1>
      <Counter />
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
