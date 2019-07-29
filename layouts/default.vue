<template>
  <div>
    <TheHeader></TheHeader>
    <nuxt />
  </div>
</template>

<script>
import TheHeader from "@/components/layout/header/TheHeader";
export default {
  components: {
    TheHeader
  }
};
</script>
