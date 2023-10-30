<template>
  <MainLayout :nav="false">
    <nuxt-link :to="{ path: 'Home' }">goHome</nuxt-link>
  </MainLayout>
</template>

<script setup>

 
import MainLayout from '~/layouts/MainLayout.vue'
</script>
