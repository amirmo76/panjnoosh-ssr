<template>
  <nav>
    <ul>
      <li>
        <nuxt-link to="/shop" class="link">فروشگاه</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/#special-offers" class="link">پیشنهادات ویژه</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/blog" class="link">بلاگ</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about" class="link">درباره ما</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/contact" class="link">ارتباط با ما</nuxt-link>
      </li>
    </ul>
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

ul {
  list-style-type: none;
  display: flex;
}

li {
  transition: all 0.2s;
  display: flex;
  align-items: center;
}

.link {
  display: block;
  padding: $header-link-padding;
  position: relative;
  transition: all 0.2s;
}

.link:hover {
  color: $primary;
}
</style>
