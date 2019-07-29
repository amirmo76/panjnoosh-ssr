<template>
  <div :class="{header: true, light: light}">
    <nuxt-link class="logo-container" to="/">
      <Logo :class="{logo: true, dark: light}" />
    </nuxt-link>
    <HeaderNavigation class="nav"></HeaderNavigation>
    <HeaderAccount class="account" :isLoggedIn="false" :avatar="'/images/profile.png'"></HeaderAccount>
  </div>
</template>

<script>
import HeaderNavigation from "./HeaderNavigation";
import HeaderAccount from "./HeaderAccount";
import Logo from "@/assets/svg/logo.svg";
// import { mapGetters } from "vuex";

export default {
  name: "Header",
  components: {
    Logo,
    HeaderNavigation,
    HeaderAccount
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
  align-items: center;
  direction: rtl;
  height: $header-height;
  padding: $container-padding;

  &.light {
    background-color: $light;
    color: $grey;
  }
}

.logo {
  margin-left: $header-logo-margin;
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


