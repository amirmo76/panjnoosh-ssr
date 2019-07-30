<template>
  <nav>
    <nuxt-link to="/shop" class="link">فروشگاه</nuxt-link>
    <nuxt-link to="/#special-offers" class="link">پیشنهادات ویژه</nuxt-link>
    <nuxt-link to="/blog" class="link">بلاگ</nuxt-link>
    <nuxt-link to="/about" class="link">درباره ما</nuxt-link>
    <nuxt-link to="/contact" class="link">ارتباط با ما</nuxt-link>
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
