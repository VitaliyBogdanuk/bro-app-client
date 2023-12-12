<template>
  <MainLayout :nav="true">
    <div v-if="topicsInfo" id="topic">
      <div class="topic_wraper">
        <div class="title">
          <h1>{{ topicsInfo.title }}</h1>
          <img
            class="topicImage"
            src="..//src/assets/singleTopics/fox_topic.png"
            alt="fox_topic"
          />
        </div>
        <div class="topic_about">
          <h3>{{ category }}</h3>
          <div class="question_number">
            <div class="number_circle">?</div>
            <p class="number_info">{{ amountQuestions }} питань</p>
            <div>
              <img src="..//src/assets/singleTopics/Line.svg" alt="line" />
            </div>
            <div class="number_circle">
              <img
                src="..//src/assets/singleTopics/pointsImage.png"
                alt="points"
              />
            </div>
            <p class="number_info">{{ score }} балів</p>
          </div>
          <p class="description_title">ОПИС</p>
          <div class="text_background">
            <p class="text">
              {{ topicsInfo.description }}
            </p>
          </div>
          <button class="button-big">СТАРТУЄМО</button>
        </div>
      </div>
    </div>
  </MainLayout>
</template>

<script>
import MainLayout from '~/layouts/MainLayout.vue'
export default {
  name: 'singleTopic',
  components: {
    MainLayout,
  },
  data() {
    return {
      topicsInfo: null,
      category: '',
      amountQuestions: null,
      score: null,
    }
  },
  async mounted() {
    const id = this.$route.params.id
    this.category = this.$route.params.category
    await this.$axios
      .get(`/api/topic/${id}`, {
        withCredentials: true,
      })
      .then((response) => {
        this.topicsInfo = response.data
        this.amountQuestions = this.topicsInfo.situations.length
        this.score = this.topicsInfo.situations.length * 10
        console.log(this.topicsInfo)
      })
      .catch((error) => {
        console.log(error)
      })
  },
}
</script>

<style>
#topic {
  max-width: 375px;
  height: calc(100vh - 90px);
}

.topic_wraper .title {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding: 0;
  margin-bottom: 96px;
}

.topic_wraper .title h1 {
  padding-left: 41px;
}

.topic_wraper .topicImage {
  max-width: 140px;
}

.topic_wraper .topic_about {
  background: var(--bg_color_profile);
  max-width: 353px;
  height: 100%;
  border-radius: 15px;
  margin: 0 auto;
}
.topic_wraper .topic_about .description_title {
  font-size: 14px;
  color: var(--dark_blue);
  margin-bottom: 5px;
}

.topic_wraper .topic_about .question_number {
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-around;
  background: var(--img_fon_users);
  max-width: 300px;
  height: 40px;
  border-radius: 15px;
  margin-bottom: 15px;
}
.topic_wraper .topic_about .question_number .number_circle {
  width: 34px;
  height: 34px;
  border-radius: 50px;
  background: var(--grey_color_2);
  color: var(--text_color_black);
  font-size: 24px;
  font-weight: bold;
  display: flex;
  justify-content: center;
  align-items: center;
}

.topic_wraper .topic_about {
  padding: 10px 10px 20px 10px;
}

.topic_wraper .topic_about h3 {
  font-size: 16px;
  color: var(--grey_color_2);
  margin-bottom: 10px;
}

.topic_wraper .topic_about .question_number .number_circle img {
  width: 25px;
}

.topic_wraper .topic_about .text_background {
  margin: 0 auto;
  max-width: 300px;
  background: var(--font_color);
  border-radius: 15px;
  border: 1px solid var(--img_fon_users);
  margin-bottom: 20px;
  padding: 10px;
}

.topic_wraper .topic_about .text_background .text {
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
}

.topic_wraper .topic_about .button-big {
  display: block;
  margin: 0 auto;
  max-width: 300px;
  height: 50px;
}

.topic_wraper .topic_about .question_number .number_info {
  font-size: 12px;
  color: var(--dark_blue);
  font-weight: 500;
}
</style>