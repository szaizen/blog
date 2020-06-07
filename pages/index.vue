<template>
  <div class="container">
    <div>
      <ArticleCard v-for="(article, index) in articles" :key="index" :article="article" :index="index" />
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import ArticleCard from '../components/card/ArticleCard';

export default Vue.extend({

  data() {
    return {
      articles: null
    }
  },

  components: {
    ArticleCard
  },

  async asyncData() {
      const api_url = process.env.API_URL + 'article';
      const response = await axios.get(api_url, { headers: { 'X-API-KEY': process.env.API_KEY } });
      return {
				articles: response.data['contents']
			};
  }

})
</script>

<style>

</style>
