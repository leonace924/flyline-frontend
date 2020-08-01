<template>
  <ul class="navbar__elements">
    <li>
      <router-link :to="{ name: 'How it works' }">Features</router-link>
    </li>
    <li>
      <router-link :to="{ name: 'Pricing' }">Premium</router-link>
    </li>
  </ul>
</template>

<script>
export default {
  name: "NavbarElements"
};
</script>

<style lang="scss">
.navbar__elements {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;

  li {
    padding: 0 22px;
    display: inline-flex;
    justify-content: center;
    align-items: center;
  }

  a {
    text-decoration: none;
    font-family: "Gilroy-Bold";
    font-size: 15px;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.44;
    letter-spacing: normal;
    text-align: left;
    color: #3a3f5c;
  }
}
</style>
