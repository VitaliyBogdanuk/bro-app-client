<template>
  <div class="nav-bar">
    <button class="back-button" @click="goBack()"></button>
    <button class="menu-button"></button>
    <nuxt-link to="/Home"><button class="home-button"></button></nuxt-link>
  </div>
</template>
<script>
export default {
  name: 'NavBar',
  methods: {
    goBack(){
      this.$router.back();
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
</style>
