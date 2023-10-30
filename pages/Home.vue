<template>
  <MainLayout :nav="true">
    <div class="home-wraper">
      <p class="title">Привіт</p>
      <p class="title-name">Ірина</p>
      <div class="test">
        <img src="../src/assets/home/fox-1.png" alt="Fox" />
        <div class="test-background"></div>
      </div>
      <div class="test">
        <div class="test-background"></div>
        <img src="../src/assets/home/fox-2.png" alt="Fox" />
      </div>
      <div class="test">
        <img src="../src/assets/home/enot.png" alt="Fox" />
        <div class="test-background"></div>
      </div>
      <button class="button-big reviews-button">
        <p class="reviews-title">Залиште відгук щоб наш Лис став ще кращим</p>
      </button>
    </div>
  </MainLayout>
</template>
<script>
import MainLayout from '~/layouts/MainLayout.vue'
export default {
  name: 'Home',
  components: {
    MainLayout,
  },
}
</script>
<style>
.title {
  color: var(--white_color);
  font-size: 16px;
  font-weight: 500;
  line-height: 150%;
  padding-left: 22px;
}
.title-name {
  color: var(--white_color);
  font-size: 24px;
  font-weight: 500;
  padding-left: 22px;
  margin-bottom: 16px;
}
.test img {
  width: 100px;
  height: 100px;
}
.test {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 20px;
}
.test-background {
  width: 220px;
  height: 120px;
  background-color: var(--white_color);
  border-radius: 15px;
  border: 1px solid var(--button_color);
}
.reviews-button {
  display: block;
  margin: 0 auto;
  width: 300px;
  height: 50px;
  padding: 4px 62px 4px 62px;
}
.reviews-title {
  color: var(--white_color);
  text-align: center;
  font-size: 14px;
}
</style>
