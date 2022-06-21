<template>
  <div class="container submit-container">
    <img
      src="./icons/illustration-thank-you.svg"
      alt="illustration of a transaction being made"
      class="submit--illustration"
    />
    <span class="submit--rating">You selected {{ rating }} out of 5</span>
    <h2 class="card--title submit--title">Thank you!</h2>
    <p class="card--description submit--description">
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
.submit-container {
  position: absolute;
  top: 0;
  justify-content: center;
  align-items: center;
}

.submit--illustration {
  margin-top: 10px;
  margin-bottom: 22px;
}

.submit--rating {
  width: 167px;
  height: 32px;
  padding: 9px;
  margin-bottom: 27px;
  border-radius: 25px;
  background: var(--medium-grey);
  font-size: 1.4rem;
  letter-spacing: 0.01rem;
  color: var(--accent-color);
}

.submit--title {
  margin-bottom: 14px;
}

.submit--description {
  margin-bottom: 0;
  text-align: center;
}
</style>
