<template>
  <ul class="navbar__entry">
    <li class="navbar__login">
      <Button class="btn" @click.prevent.stop="toggleStartForm">Login</Button>
      <SlideXLeftTransition :delay="100">
        <StartForm v-if="showStart" @close="showStart = false" />
      </SlideXLeftTransition>
    </li>
    <li>
      <router-link to="/register" class="btn btn--primary">Sign Up</router-link>
    </li>
  </ul>
</template>

<script>
import Button from "@/components/atoms/Button";
import StartForm from "@/components/molecules/StartForm";
import { SlideXLeftTransition } from "vue2-transitions";

export default {
  name: "NavbarEntry",
  data() {
    return {
      showStart: false
    };
  },
  methods: {
    toggleStartForm() {
      this.showStart = !this.showStart;
    }
  },
  components: {
    Button,
    StartForm,
    SlideXLeftTransition
  }
};
</script>

<style lang="scss">
.navbar__entry {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
  margin-left: auto;

  li {
    &:first-child {
      margin-right: 15px;
    }

    a,
    button {
      width: 90px;
      height: 40px;
      border-radius: 30px !important;
      font-size: 15px;
      font-family: "Gilroy-Bold";
      &:focus {
        outline: none;
      }
    }

    button {
      color: #0e3178;
    }
  }
}

.navbar__login {
  position: relative;
}
</style>
