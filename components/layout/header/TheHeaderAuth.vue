<template>
  <div class="container">
    <div v-if="isLoggedIn" class="flex">
      <nuxt-link to="/dashboard">
        <div class="avatar" :style="{backgroundImage: `url(${avatar})`}"></div>
      </nuxt-link>
      <Button type="text" round color="white" size="sm" class="cart">
        <template #icon>
          <cart />
        </template>
      </Button>
      <Button type="text" round color="white" size="sm" class="logout">
        <template #icon>
          <logout />
        </template>
      </Button>
    </div>

    <div v-else class="flex">
      <nuxt-link to="/register" class="link">ثبت نام</nuxt-link>
      <nuxt-link to="/login" class="link">ورود</nuxt-link>
    </div>
  </div>
</template>

<script>
import Button from '@/components/base/Button';
import cart from "@/assets/svgs/cart.svg";
import logout from "@/assets/svgs/logout.svg";

export default {
  name: "TheHeaderAauth",
  components: {
    Button,
    cart,
    logout
  },
  props: {
    isLoggedIn: {
      type: Boolean,
      required: true
    },
    avatar: {
      type: String,
      default: "/images/profile.png"
    }
  },
  methods: {
    async logout() {
      // this.$q.loadingBar.start();
      await this.$store.dispatch("logout");
      // this.$q.loadingBar.stop();
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~assets/styles/variables';

.container 
  display flex
  align-items stretch

.flex 
  display flex
  align-items center

.sign-icon 
  fill $white
  margin $header-sign-icon-margin

.link 
  padding $header-link-padding
  transition all 0.2s
  display block
  position relative
  align-self stretch
  display flex
  align-items center
  &:hover 
    color: $primary

.avatar 
  width $header-avatar-size
  height $header-avatar-size
  margin $header-avatar-margin
  position relative
  background-size cover
  background-position center
  border-radius $header-avatar-border-radius
  &:hover
    cursor pointer

.cart 
  margin $header-cart-margin

.logout 
  transform rotate(180deg)
  &:hover 
    fill $primary
    cursor pointer
</style>

