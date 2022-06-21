<template>
  <div class="main-card">
    <figure class="star-icon">
      <img src="./icons/icon-star.svg" alt="" />
    </figure>
    <h2 class="main-card__title">How did we do?</h2>
    <p class="main-card__description">
      Please let us know how we did with your support request. All feedback is
      appreciated to help us improve our offering!
    </p>
    <div class="rating">
      <button
        type="button"
        class="rating__btn"
        @click="selectRating"
        v-for="(number, index) in ratings"
        :key="index"
      >
        {{ number.rating }}
      </button>
    </div>
    <button
      class="submit__btn"
      :class="{ disabledBtn: isBtnDisabled }"
      @click.prevent="submitRating"
      :disabled="isBtnDisabled"
    >
      Submit
    </button>
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
      isBtnDisabled: true,
    };
  },
  methods: {
    selectRating(ratings) {
      const index = ratings.target.__vnode.key; // only way I found to make the index dynamic
      this.$emit("rating-selected", this.ratings[index].rating);
      this.isBtnDisabled = false;
    },
    submitRating() {
      this.$emit("rating-submitted");
    },
  },
};
</script>

<style>
.main-card {
  display: flex;
  flex-direction: column;
  width: 326px;
  height: 358px;
  padding: 22px 24px 31px;
  background: var(--dark-blue);
  border-radius: 15px;
}

.star-icon {
  width: 40px;
  height: 40px;
  margin-bottom: 18px;
  padding: 12px;
  border-radius: 50%;
  background: var(--medium-grey);
}

.main-card__title {
  margin-bottom: 11px;
  font-size: 2.4rem;
  font-weight: 700;
  color: var(--white);
}

.main-card__description {
  margin-bottom: 27px;
  font-size: 1.4rem;
  line-height: 2.2rem;
  color: var(--light-grey);
}

.rating {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 17px;
  width: 280px;
  height: 40px;
  margin-bottom: 24px;
}

.rating__btn {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  border: none;
  background: var(--medium-grey);
  font-size: 1.4rem;
  color: var(--light-grey);
}

.rating__btn:focus {
  background: var(--accent-color);
  color: var(--white);
  outline: 0.5px solid var(--accent-color);
}

.submit__btn {
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

.submit__btn:focus {
  background: var(--white);
  color: var(--accent-color);
}

.disabledBtn {
  display: none;
}

@media (hover: hover) {
  .rating__btn:hover {
    background: var(--light-grey);
    color: var(--white);
    cursor: pointer;
  }

  .submit__btn:hover {
    background: var(--white);
    color: var(--accent-color);
    cursor: pointer;
  }
}

@media screen and (min-width: 425px) {
  .main-card {
    width: 412px;
    height: 414px;
    padding: 32px 39px 30px 30px;
    border-radius: 30px;
  }

  .star-icon {
    width: 49px;
    height: 49px;
    margin-bottom: 30px;
    padding: 16px;
  }

  .main-card__title {
    font-size: 2.8rem;
  }

  .main-card__description {
    font-size: 1.5rem;
    line-height: 2.3rem;
  }

  .rating {
    gap: 22px;
    width: 341px;
    height: 51px;
    margin-bottom: 32px;
  }

  .rating__btn {
    width: 51px;
    height: 51px;
    font-size: 1.5rem;
  }

  .submit__btn {
    width: 341px;
    font-size: 1.5rem;
  }
}
</style>
