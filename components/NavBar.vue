<template>
  <div class="nav-bar">
    <button class="back-button fade-in" @click="goBack()"></button>
    <button class="menu-button fade-in" @click="openModal"></button>
    <nuxt-link to="/Home"><button class="home-button fade-in"></button></nuxt-link>
    <ModalMenu v-if="isModalOpen" @close="closeModal" />
  </div>
</template>
<script>
import ModalMenu from '~/components/ModalMenu.vue';

export default {
  name: 'NavBar',
  components: {
    ModalMenu
  },
  data() {
    return {
      isModalOpen: false
    };
  },
  methods: {
    goBack() {
      this.$router.back();
    },
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
    }
  }
}
</script>

<style>
.nav-bar {
  background-color: var(--white_color);
  max-width: 375px;
  height: 90px;
  display: flex;
  justify-content: center;
  align-items: center;
  justify-content: space-around;
  border-radius: 15px 15px 0px 0px;
  margin: 0 auto;
}
.back-button {
  background: url(../src/assets/nav/back.png);
  background-size: cover;
  width: 40px;
  height: 40px;
  border: none;
}
.menu-button {
  background: url(../src/assets/nav/burger.png);
  width: 80px;
  height: 80px;
  background-size: cover;
  border: none;
}
.home-button {
  background: url(../src/assets/nav/home.png);
  width: 50px;
  height: 50px;
  background-size: cover;
  border: none;
}

.fade-in {
  animation-name: fade-in;
  animation-duration: 0.7s;
  animation-fill-mode: forwards;
}
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>