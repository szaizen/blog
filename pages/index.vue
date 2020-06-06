<template>
  <div class="container">
    <div>
      <ul>
        <li v-for="(article, index) in articles" :key="index">
          {{ article.createdAt }}
          {{ article.title }}
          {{ article.category.name }}
          {{ article.Image.url }}

          <nuxt-link :to="'/article/' + article.id">link</nuxt-link>

        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'

export default Vue.extend({

  data() {
    return {
      articles: null
    }
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
