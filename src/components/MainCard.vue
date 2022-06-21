<template>
  <div class="container">
    <figure class="star-icon--container">
      <img src="./icons/icon-star.svg" alt="" />
    </figure>
    <h2 class="card--title">How did we do?</h2>
    <p class="card--description">
      Please let us know how we did with your support request. All feedback is
      appreciated to help us improve our offering!
    </p>
    <div class="rating--container">
      <button
        type="button"
        class="rating-btn"
        @click="selectRating"
        v-for="(number, index) in ratings"
        :key="index"
      >
        {{ number.rating }}
      </button>
    </div>
    <button class="submit-btn" @click.prevent="submitRating">Submit</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ratings: [
        { rating: 1 },
        { rating: 2 },
        { rating: 3 },
        { rating: 4 },
        { rating: 5 },
      ],
    };
  },
  methods: {
    selectRating(ratings) {
      const index = ratings.target.__vnode.key; // only way I found to make the index dynamic
      this.$emit("rating-selected", this.ratings[index].rating);
    },
    submitRating() {
      this.$emit("rating-submitted");
    },
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  width: 326px;
  height: 358px;
  padding: 22px 24px 31px;
  background: var(--dark-blue);
  border-radius: 15px;
}

.star-icon--container {
  width: 40px;
  height: 40px;
  margin-bottom: 18px;
  padding: 12px;
  border-radius: 50%;
  background: var(--medium-grey);
}

.card--title {
  margin-bottom: 11px;
  font-size: 2.4rem;
  font-weight: 700;
  color: var(--white);
}

.card--description {
  margin-bottom: 27px;
  font-size: 1.4rem;
  line-height: 2.2rem;
  color: var(--light-grey);
}

.rating--container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 17px;
  width: 280px;
  height: 40px;
  margin-bottom: 24px;
}

.rating-btn {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  border: none;
  background: var(--medium-grey);
  font-size: 1.4rem;
  color: var(--light-grey);
}

.rating-btn:focus {
  background: var(--accent-color);
  color: var(--white);
  outline: 0.5px solid var(--accent-color);
}

.submit-btn {
  width: 279px;
  height: 45px;
  border-radius: 25px;
  border: none;
  background: var(--accent-color);
  font-size: 1.4rem;
  letter-spacing: 0.15rem;
  text-transform: uppercase;
  color: var(--white);
}

.submit-btn:focus {
  background: var(--white);
  color: var(--accent-color);
}

@media (hover: hover) {
  .rating-btn:hover {
    background: var(--light-grey);
    color: var(--white);
    cursor: pointer;
  }

  .submit-btn:hover {
    background: var(--white);
    color: var(--accent-color);
    cursor: pointer;
  }
}
</style>
