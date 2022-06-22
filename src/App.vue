<script setup>
import FeedbackCard from "./components/FeedbackCard.vue";
</script>

<template>
  <main>
    <FeedbackCard></FeedbackCard>
  </main>
</template>

<style>
@import "./assets/base.css";

#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: var(--very-dark-blue);
}

main {
  position: relative;
}
</style>
