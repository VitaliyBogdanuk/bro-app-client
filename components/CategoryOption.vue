<template>
  <div class="categ-wraper">
    <div class="categ-icon">
      <img
        :src="require('../src/assets/categories/icons/' + category.image)" alt="money"
      />
    </div>
    <div>
      <button class="button-big">{{category.title  }}</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CategoriOption',
  props: {
    category: {
        type: Object,
        default() {},
    },
  }
}
</script>
<style scoped>
.categ-wraper {
  display: flex;
  flex-direction: column;
  width: 80px;
  align-items: center;
  cursor: pointer;
}
.categ-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  flex-shrink: 0;
  border-radius: 15px;
  background:var(--category_bg);
}
.categ-icon img {
  width: 40px;
}
.button-big {
  background-color: transparent;
  width: 100%;
  padding: 0;
  font-size: 14px;
  font-style: normal;
}
</style>
