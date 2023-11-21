<template>
  <MainLayout :nav="true">
    <div class="home-wraper">
      <div>
        <h1 class="title">Привіт</h1>
        <p class="title-name">Ірина</p>
      </div>
      <div class="test">
        <img src="../src/assets/home/fox-1.png" alt="Fox" />
        <div class="about-background">
          <p class="test-about">
            <span class="test-title">B.R.O</span> надає змогу бути на крок
            попереду від шахраїв.Тренуйся, проходячи тести, щоб бути готовим до
            будь-якої ситуації.
          </p>
          <nuxt-link to="/categories"><button class="button-big about-button">ПРОЙТИ ТЕСТУВАННЯ</button></nuxt-link>
          
        </div>
      </div>
      <div class="test">
        <div class="speak-background">
          <p class="test-about">
            Якщо ти потрапив у складну ситуацію та не можеш знайти вихід - наш
            кмітливий лис завжди на зв"язку. Переходь у чат - він завжди дасть
            слушну пораду.
          </p>
          <button class="button-big about-button">ПОСПІЛКУВАТИСЯ</button>
        </div>
        <img src="../src/assets/home/fox-2.png" alt="Fox" />
      </div>
      <div class="test">
        <img src="../src/assets/home/enot.png" alt="Fox" />
        <div class="check-background">
          <p class="test-about">
            Якщо ж тобі здається, що ти вже натрапив на злодюг - гайда
            перевіряти чи то не шахрай.
          </p>
          <button class="button-big about-button">ПЕРЕВІРИТИ НОМЕР</button>
        </div>
      </div>
      <div>
        <button class="button-big reviews-button">
          <p class="reviews-title">Залиш відгук щоб наш Лис став ще кращим</p>
        </button>
      </div>
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
.home-wraper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: calc(100vh - 90px);
  max-width: 375px;
  padding: 20px 11px 40px 11px;
}
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
}
.test img {
  width: 100px;
  height: 100px;
}
.test {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.about-background {
  width: 220px;
  height: 120px;
  background-color: var(--white_color);
  border-radius: 15px;
  border: 1px solid var(--button_color);
  padding: 10px 10px 10px 10px;
}
.speak-background {
  width: 220px;
  height: 140px;
  background-color: var(--white_color);
  border-radius: 15px;
  border: 1px solid var(--button_color);
  padding: 10px 10px 10px 10px;
}
.check-background {
  width: 220px;
  height: 110px;
  background-color: var(--white_color);
  border-radius: 15px;
  border: 1px solid var(--button_color);
  padding: 10px 10px 10px 10px;
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
.test-title {
  color: var(--text_color);
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
}
.test-about {
  color: var(--text_color);
  font-size: 12px;
  line-height: 130%;
  margin-bottom: 5px;
}
.about-button {
  width: 200px;
  height: 30px;
  text-align: center;
  padding: 0px;
}
</style>
