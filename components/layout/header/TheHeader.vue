<template>
  <header :class="{header: true, light: light}">
    <nuxt-link class="logo-container" to="/">
      <Logo :class="{logo: true, dark: light}" />
    </nuxt-link>
    <TheHeaderNavigation class="nav"></TheHeaderNavigation>
    <TheHeaderAuth class="account" :isLoggedIn="true" :avatar="'/images/profile.png'"></TheHeaderAuth>
  </header>
</template>

<script>
import TheHeaderNavigation from "./TheHeaderNavigation";
import TheHeaderAuth from "./TheHeaderAuth";
import Logo from "@/assets/svgs/logo.svg";
// import { mapGetters } from "vuex";

export default {
  name: "TheHeader",
  components: {
    Logo,
    TheHeaderNavigation,
    TheHeaderAuth
  },
  data() {
    return {
      light: false
    };
  }
  // computed: {
  //   ...mapGetters(["isLoggedIn"])
  // }
};
</script>

<style lang="stylus" scoped>
@import '~assets/styles/variables';

.header {
  font-size: $font-size;
  background-color: $black;
  color: $light;
  display: flex;
  align-items: stretch;
  direction: rtl;
  height: $header-height;
  padding: $container-padding;

  &.light {
    background-color: $light;
    color: $grey;
  }
}

.logo {
  margin: $header-logo-margin;
  fill: $primary;
  height: $header-logo-height;

  &.dark {
    fill: $grey;
  }
}

.logo-container {
  display: flex;
  align-items: center;
}

.nav {
  margin-left: auto;
}
</style>


