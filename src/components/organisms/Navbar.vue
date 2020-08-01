<template>
  <nav class="nav">
    <div class="navbar">
      <NavbarLogo />
      <NavbarElements />

      <div class="navbar__links">
        <NavbarNav />
        <NavbarEntry v-if="user.anonymous" />
        <NavbarUser v-else />
      </div>
    </div>
  </nav>
</template>

<script>
import Vuex from "vuex";
import NavbarElements from "@/components/molecules/NavbarElements";
import NavbarNav from "@/components/molecules/NavbarNav";
import NavbarLogo from "@/components/molecules/NavbarLogo";
import NavbarUser from "@/components/molecules/NavbarUser";
import NavbarEntry from "@/components/molecules/NavbarEntry";

export default {
  name: "Navbar",
  components: {
    NavbarElements,
    NavbarNav,
    NavbarLogo,
    NavbarUser,
    NavbarEntry
  },
  computed: {
    ...Vuex.mapState("user", ["user"])
  }
};
</script>

<style lang="scss">
@import "@/styles/app.scss";

.nav {
  @include xy-grid();
  @include flex-align(center, center);

  background-color: #ffffff;
  box-shadow: 0 5px 30px 0 rgba(26, 25, 25, 0.03);
  width: 100%;
  flex-grow: 1;
  height: 90px;
  position: sticky;
  top: 0;
  z-index: 100;
}

.navbar {
  // position: fixed;
  width: 960px;
  height: 49px;
  margin: 0 auto;

  @include xy-grid();
  @include flex-align(left, center);

  &__logo {
    padding-right: 40px;

    img {
      width: 100px;
      height: 20px;
      object-fit: contain;
    }
  }

  &__links {
    @include xy-grid();
    @include flex-align(left, center);
    flex-grow: 1;
  }
}
</style>
