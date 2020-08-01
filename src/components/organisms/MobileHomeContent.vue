<template>
  <div class="mobile__home__content">
    <h1
      class="mobile__home__content__title"
      style="margin-top: 60px;margin-bottom: 40px;"
    >
      Ready to put your travel planning on auto-pilot?
    </h1>
    <p class="mobile__home__content__description">
      We're making a few updates, check back soon for the easiest way to search,
      book, and manage flights.
    </p>
    <div class="mobile__home__content__applink">
      <div class="mobile__home__content__applink__wrapper">
        <AppLink
          :image="'playstore.png'"
          :source="'on Google Play'"
          :comment="'Available soon'"
        />
      </div>
      <div
        class="mobile__home__content__applink__wrapper mobile__home__content__applink__wrapper--right"
      >
        <AppLink
          :image="'apple.png'"
          :source="'on App Store'"
          :comment="'Available soon'"
        />
      </div>
    </div>
    <p class="mobile__home__content__login">
      Questions? Send us an email to hello@flyline.io and we'll get back to you.
    </p>
  </div>
</template>

<script>
import AppLink from "@/components/molecules/AppLink";

export default {
  name: "MobileHomeContent",
  components: {
    AppLink
  }
};
</script>

<style lang="scss">
.mobile__home__content {
  padding: 0 30px;
  &__title {
    font-family: Gilroy-Bold;
    font-size: 32px;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.19;
    letter-spacing: normal;
    text-align: center;
    color: #0e3178;
    margin-top: 30px;
    padding: 0 20px;
  }
  &__description {
    font-family: Gilroy-Medium;
    font-size: 16px;
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.5;
    letter-spacing: normal;
    text-align: center;
    color: #8e969f;
    margin-top: 20px;
  }
  &__applink {
    display: flex;
    padding: 20px 0;
    border-bottom: 1px solid #e7e9f0;
    &__wrapper {
      flex: 1;
      &--right {
        display: flex;
        justify-content: flex-end;
      }
    }
  }
  &__login {
    font-family: Gilroy-Medium;
    font-size: 14px;
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.86;
    letter-spacing: normal;
    text-align: center;
    color: #8e969f;
    margin-top: 20px;
    .highlight {
      color: #00aeef;
    }
  }
}
</style>
