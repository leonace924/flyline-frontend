<template>
  <ul class="navbar__nav">
    <li v-if="user.anonymous">
      <router-link :to="{ name: 'How it works' }">How it works</router-link>
    </li>
    <li v-if="user.anonymous">
      <router-link :to="{ name: 'Pricing' }">Memberships</router-link>
    </li>
  </ul>
</template>

<script>
export default {
  name: "NavbarNav"
};
</script>

<style lang="scss">
.navbar__nav {
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
    color: #0e3178;
  }
}
</style>
