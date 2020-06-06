<template>
  <div>
    {{ article }}
  </div>
</template>

<script>

import Vue from 'vue'
import axios from 'axios'

export default Vue.extend({

  data() {
    return {
      article: null
    }
  },

  async asyncData({ params }) {
      const api_url = process.env.API_URL + 'article/' + params.id;
      const response = await axios.get(api_url, { headers: { 'X-API-KEY': process.env.API_KEY } });
      return {
				article: response['data']
			};
  }
})
</script>

<style lang="scss" scoped>
</style>
