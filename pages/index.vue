<template>
  <MainLayout :nav="false">
    <nuxt-link :to="{ path: 'Home' }">goHome</nuxt-link>
  </MainLayout>
</template>

<script>
import MainLayout from '~/layouts/MainLayout.vue'
export default {
  name: 'IndexPage',
  comments:{
    MainLayout,
  }
}
</script>
