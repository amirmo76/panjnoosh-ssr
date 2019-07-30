<template>
  <nav>
    <nuxt-link to="/shop" class="link" v-ripple>فروشگاه</nuxt-link>
    <nuxt-link to="/#special-offers" class="link" v-ripple>پیشنهادات ویژه</nuxt-link>
    <nuxt-link to="/blog" class="link" v-ripple>بلاگ</nuxt-link>
    <nuxt-link to="/about" class="link" v-ripple>درباره ما</nuxt-link>
    <nuxt-link to="/contact" class="link" v-ripple>ارتباط با ما</nuxt-link>
  </nav>
</template>

<script>
export default {
  name: "TheHeaderNavigation"
};
</script>

<style lang="stylus" scoped>
@import '~assets/styles/variables';

nav {
  display: flex;
  align-items: stretch;
}

.link {
  display: flex;
  align-items: center;
  padding: $header-link-padding;
  position: relative;
  transition: all 0.2s;

  &:hover {
    color: $primary;
  }
}
 </style>
