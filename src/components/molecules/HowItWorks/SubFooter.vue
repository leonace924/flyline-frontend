<template>
  <div
    style="margin-top: 150px; margin-bottom: 100px;"
    class="hero hero--footer"
  >
    <div class="hero__header">
      <h4 class="hero__subtitle">
        Don't miss out on the savings
      </h4>
      <h3 class="hero__title">
        Get started with FlyLine Today
      </h3>
    </div>
    <div class="hero__links">
      <Button type="primary" @click="goTo('Pricing')">Sign Up for Free</Button>
      <Button type="primary" @click="goTo('How it works')"
        >Download the App</Button
      >
    </div>
  </div>
</template>

<script>
import Button from "@/components/atoms/Button.vue";

export default {
  name: "SubFooter",
  components: {
    Button
  },
  methods: {
    goTo(page) {
      this.$router.push({ name: page });
    }
  }
};
</script>

<style scoped lang="scss">
.hero {
  &--footer {
    display: flex;
    flex-flow: row wrap;
    align-items: center;
    justify-content: space-between;
    color: #ffffff;
    background-color: #0e3178;
    border-radius: 1rem;
    padding: 4rem;
    flex-grow: 1;
    box-shadow: 5px 5px 50px 0 rgba(14, 49, 120, 0.3);

    .hero {
      &__title {
        font-size: 1.5rem;
        font-family: "Gilroy-Bold", sans-serif;
        font-weight: 400;
        margin: 0;
        padding-bottom: 0;
      }

      &__subtitle {
        font-size: 0.75rem;
        text-transform: uppercase;
        letter-spacing: 0.15rem;
        font-family: "Gilroy-Light", sans-serif;
        margin: 0;
        padding-bottom: 0.5rem;
      }

      &__links {
        display: flex;
        justify-content: center;
        align-items: center;

        > .btn {
          width: auto;
          height: auto;
          padding: 0.8rem 1.6rem;
          box-shadow: none;
          font-size: 0.7rem;

          &--outline {
            color: #ffffff;
            border-color: #ffffff;
            opacity: 0.5;
          }

          &:first-child {
            margin-right: 1rem;
          }
        }
      }
    }
  }
}
</style>
