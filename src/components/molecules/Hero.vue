<template>
  <div class="hero">
    <div class="hero__title">
      <slot name="title"></slot>
    </div>
    <div class="hero__description">
      <slot name="description"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero"
};
</script>

<style lang="scss">
.hero {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: center;
  color: #ffffff;
  background-color: #0e3178;
  border-radius: 1rem;
  padding: 3.5rem 0;
  flex-grow: 1;

  &__title {
    font-size: 2rem;
    padding-bottom: 0.5rem;
  }

  &__description {
    width: 38rem;
    font-size: 0.75rem;
    text-align: center;
    line-height: 1.8;
  }
}
</style>
