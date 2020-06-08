<template>
  <div class="category">
    <h1 class="category_title">#{{ category }}の記事一覧</h1>
    <ArticleCard v-for="(article, index) in articles" :key="index" :article="article" :index="index" />
    <div v-if="articles.length === 0">まだこのカテゴリーの記事は投稿されていません。</div>
  </div>
</template>

<script>

import Vue from 'vue'
import axios from 'axios'
import ArticleCard from '../../components/card/ArticleCard'

export default Vue.extend({

  data() {
    return {
      articles: null,
      category: null
    }
  },

  components: {
    ArticleCard
  },

  async asyncData({ params }) {
    const api_url = process.env.API_URL + 'article?filters=category[equals]' + params.id;
    const response = await axios.get(api_url, { headers: { 'X-API-KEY': process.env.API_KEY } });

    const category_api_url = process.env.API_URL + 'categorys/' + params.id;
    const category_response = await axios.get(category_api_url, { headers: { 'X-API-KEY': process.env.API_KEY } });

    return {
      articles: response['data']['contents'],
      category: category_response['data'].name
    };
  }
})
</script>

<style lang="scss" scoped>
.category_title {
  position: relative;
  padding: 0.5em;
  background: #a6d3c8;
  color: white;
  font-size: 22px;
  margin-bottom: 40px;
  &:after {
    position: absolute;
    content: '';
    top: 100%;
    left: 0;
    border: none;
    border-bottom: solid 15px transparent;
    border-right: solid 20px rgb(149, 158, 155);
  }
}
</style>
