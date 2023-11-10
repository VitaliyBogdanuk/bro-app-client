<template>
  <div>
    <main>
      <slot></slot>
      <NavBar v-if="nav" />
    </main>
  </div>
</template>
<script>
import NavBar from '~/components/NavBar.vue'
export default {
  name: 'MainLayout',
  comments: {
    NavBar,
  },
  props: {
    nav: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style>
main {
  margin: 0 auto;
  background-color: var(--primary_color);
  max-width: 375px;
}
</style>
