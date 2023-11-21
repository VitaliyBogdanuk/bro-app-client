<template>
  <div>
    <MainLayout :nav="true">
      <div>
        <h1>ОБЕРІТЬ КАТЕГОРІЮ</h1>
        <div class="category-wraper">
          <div
            v-for="(categoryEvery, i) in categories"
            :key="i"
            class="category-single"
          >
            <CategoryOption :category="categoryEvery" />
          </div>
        </div>
      </div>
    </MainLayout>
  </div>
</template>
<script>

import CategoryOption from '~/components/CategoryOption.vue'
import MainLayout from '~/layouts/MainLayout.vue'

export default {
  name: 'Home',
  components: {
    MainLayout,
    CategoryOption,
  },
  data() {
    return {
      categories: [],
    }
  },
  async mounted() {
    await this.$axios
      .get(`/api/categories`, {
        withCredentials: true,
      })
      .then((response) => {
        this.categories = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  },
  methods: {},
}
</script>
<style>
.category-wraper {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  margin: 0 auto;
  padding: 0px 40px;
}
.category-single {
  padding: 20px;
  margin: 0 auto;
}
</style>
