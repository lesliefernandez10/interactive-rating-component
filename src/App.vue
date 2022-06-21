<script setup>
import MainCard from "./components/MainCard.vue";
import SubmitCard from "./components/SubmitCard.vue";
</script>

<template>
  <main>
    <MainCard
      @rating-selected="passRating"
      @rating-submitted="cardVisible"
    ></MainCard>
    <SubmitCard :rating="rating" v-show="isVisible"></SubmitCard>
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
  methods: {
    passRating(rating) {
      this.rating = rating;
    },
    cardVisible() {
      this.isVisible = true;
    },
  },
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
