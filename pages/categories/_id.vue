<template id="single_category">
  <MainLayout :nav="true">
    <div v-if="categoryInfo" class="wraper_singleCategory">
      <h1>{{ categoryInfo.title }}</h1>
      <div class="description">
        <h2>Готовий до пригод?</h2>
        <div class="about">
          <p>Тоді швидше обирай тему!</p>
          <img
            src="../../src/assets/singlePageCategory/Fox4.png"
            alt="fox_guard"
          />
        </div>
      </div>
      <img
        class="arrowDown"
        src="../../src/assets/singlePageCategory/ArrowDown.svg"
        alt="arrow"
      />

      <div
        v-for="(topic, index) in categoryInfo.topics"
        :key="index"
        class="button-big"
      >
        <nuxt-link :to="{ name: 'singleTopics', params: { id: topic.id , category: categoryInfo.title} }">
          <div class="button_text_color">
            <p>{{ topic.title }}</p>
          </div>
        </nuxt-link>
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
  data() {
    return {
      categoryInfo: null,
    }
  },
  async mounted() {
    const id = this.$route.params.id
    await this.$axios
      .get(`/api/category/${id}`, {
        withCredentials: true,
      })
      .then((response) => {
        this.categoryInfo = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  },
}
</script>

<style>
.wraper_singleCategory {
  margin: 0 auto;
  max-width: 375px;
  text-align: center;
  height: calc(100vh - 90px);
  overflow-y: scroll;
}
.wraper_singleCategory h1 {
  margin-bottom: 22px;
}
.description {
  background: var(--bg_color_profile);
  max-width: 353px;
  height: 232px;
  border-radius: 15px;
  margin: 0 auto;
  margin-bottom: 50px;
}
.description h2 {
  color: var(--text_color);
  font-size: 28px;
  text-align: center;
  padding-top: 27px;
}
.description .about {
  display: flex;
  align-items: center;
  float: inline-end;
}
.description .about p {
  font-size: 20px;
  color: var(--text_color);
  max-width: 128px;
}
.wraper_singleCategory .arrowDown {
  margin-bottom: 40px;
}
.button-big{
  margin: 20px auto;
  display: block;
  width: 300px;
  height: 50px;
}
.button_text_color{
  padding: 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var( --font_color);
  font-size: 16px;
}

</style>