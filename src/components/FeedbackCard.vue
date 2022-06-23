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
        @click="selectRating(rate)"
        v-for="(rate, index) in ratings"
        :key="index"
      >
        {{ rate.rating }}
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

  <div class="main-card submit-card" v-show="isVisible">
    <img
      src="./icons/illustration-thank-you.svg"
      alt="illustration of a transaction being made"
      class="submit-card__illustration"
    />
    <span class="submit-card__rating">You selected {{ rating }} out of 5</span>
    <h2 class="main-card__title submit-card__title">Thank you!</h2>
    <p class="main-card__description submit-card__description">
      We appreciate you taking the time to give a rating. If you ever need more
      support, don't hesitate to get in touch!
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rating: 0,
      isVisible: false,
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
    selectRating(rate) {
      this.rating = rate.rating;
      this.isBtnDisabled = false;
    },
    submitRating() {
      this.isVisible = true;
    },
  },
};
</script>

<style>
.main-card {
  display: flex;
  flex-direction: column;
  width: 32.6rem;
  height: 35.8rem;
  padding: 2.2rem 2.4rem 3.1rem;
  background: var(--dark-blue);
  border-radius: 1.5rem;
}

.star-icon {
  width: 4rem;
  height: 4rem;
  margin-bottom: 1.8rem;
  padding: 1.2rem;
  border-radius: 50%;
  background: var(--medium-grey);
}

.main-card__title {
  margin-bottom: 1.1rem;
  font-size: 2.4rem;
  font-weight: 700;
  color: var(--white);
}

.main-card__description {
  margin-bottom: 2.7rem;
  font-size: 1.4rem;
  line-height: 2.2rem;
  color: var(--light-grey);
}

.rating {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.7rem;
  width: 28rem;
  height: 4rem;
  margin-bottom: 2.4rem;
}

.rating__btn {
  width: 4.2rem;
  height: 4.2rem;
  border-radius: 50%;
  border: none;
  background: var(--medium-grey);
  font-size: 1.4rem;
  color: var(--light-grey);
}

.rating__btn:focus {
  background: var(--accent-color);
  color: var(--white);
  outline: 0.05rem solid var(--accent-color);
}

.submit__btn {
  width: 27.9rem;
  height: 4.5rem;
  border-radius: 2.5rem;
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

.submit-card {
  position: absolute;
  top: 0;
  justify-content: center;
  align-items: center;
}

.submit-card__illustration {
  margin-top: 1rem;
  margin-bottom: 2.2rem;
}

.submit-card__rating {
  width: 16.7rem;
  height: 3.2rem;
  padding: 0.9rem;
  margin-bottom: 2.7rem;
  border-radius: 2.5rem;
  background: var(--medium-grey);
  font-size: 1.4rem;
  letter-spacing: 0.01rem;
  text-align: center;
  color: var(--accent-color);
}

.submit-card__title {
  margin-bottom: 1.4rem;
}

.submit-card__description {
  margin-bottom: 0;
  text-align: center;
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
    width: 41.2rem;
    height: 41.4rem;
    padding: 3.2rem 3.9rem 3rem 3rem;
    border-radius: 3rem;
  }

  .star-icon {
    width: 4.9rem;
    height: 4.9rem;
    margin-bottom: 3rem;
    padding: 1.6rem;
  }

  .main-card__title {
    font-size: 2.8rem;
  }

  .main-card__description {
    font-size: 1.5rem;
    line-height: 2.3rem;
  }

  .rating {
    gap: 2.2rem;
    width: 34.1rem;
    height: 5.1rem;
    margin-bottom: 3.2rem;
  }

  .rating__btn {
    width: 5.1rem;
    height: 5.1rem;
    font-size: 1.5rem;
  }

  .submit__btn {
    width: 34.1rem;
    font-size: 1.5rem;
  }

  .submit-card__illustration {
    margin-top: 1.3rem;
    margin-bottom: 3.2rem;
  }

  .submit-card__rating {
    width: 19.2rem;
    margin-bottom: 3.4rem;
    font-size: 1.5rem;
    letter-spacing: 0;
  }
}
</style>
