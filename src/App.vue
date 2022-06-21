<script setup>
import MainCard from "./components/MainCard.vue";
import SubmitCard from "./components/SubmitCard.vue";
</script>

<template>
  <main>
    <MainCard></MainCard>
    <SubmitCard
      :rating="rating"
      @submit-rating-selected="submitRating"
      v-show="isVisible"
    ></SubmitCard>
  </main>
</template>

<script>
export default {
  data() {
    return {
      rating: 0,
      isVisible: false,
    };
  },
  // methods: {
  //   submitRating() {
  //     this.rating = 1;
  //     this.isVisible = !this.isVisible;
  //     console.log("You submitted your rating!");
  //   },
  // },
};
</script>

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
