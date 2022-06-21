<template>
  <div class="main-card submit-card">
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
  props: {
    rating: {
      type: Number,
    },
    isVisible: {
      type: Boolean,
    },
  },
};
</script>

<style scoped>
.submit-card {
  position: absolute;
  top: 0;
  justify-content: center;
  align-items: center;
}

.submit-card__illustration {
  margin-top: 10px;
  margin-bottom: 22px;
}

.submit-card__rating {
  width: 167px;
  height: 32px;
  padding: 9px;
  margin-bottom: 27px;
  border-radius: 25px;
  background: var(--medium-grey);
  font-size: 1.4rem;
  letter-spacing: 0.01rem;
  text-align: center;
  color: var(--accent-color);
}

.submit-card__title {
  margin-bottom: 14px;
}

.submit-card__description {
  margin-bottom: 0;
  text-align: center;
}

@media screen and (min-width: 425px) {
  .submit-card__illustration {
    margin-top: 13px;
    margin-bottom: 32px;
  }

  .submit-card__rating {
    width: 192px;
    margin-bottom: 34px;
    font-size: 1.5rem;
    letter-spacing: 0;
  }
}
</style>
