<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";
import Counter from "./components/Counter.vue";
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/counter">Counter</RouterLink>
        <RouterLink to="/notes">Notes</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  text-align: center;
}
nav {
  background-color: rgb(113, 255, 196);
  padding: 15px 20px;
  display: flex;
  gap: 1.5em;
  justify-content: center;
}
</style>
