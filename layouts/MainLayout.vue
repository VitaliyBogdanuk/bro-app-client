<template>
  <div>
    <main>
      <slot></slot>
    </main>
    <NavBar v-if="nav" />
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
  padding: 20px 11px 0px 11px;
  background-color: var(--primary_color);
  max-width: 375px;
  height: 722px;
}
</style>
