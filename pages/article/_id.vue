<template>
  <div class="article">
    <img class="image" :src="article.Image.url + '?fit=max&w=1000'" />
    <h1 class="title">{{ article.title }}</h1>
    <div class="heading">
      <div class="category">#{{ article.category.name }}</div>
      <div class="date">{{ article.publishedAt }}</div>
    </div>
    <div class="html-body" v-html="article.content"></div>
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
.article {
  padding: 20px 0;
}
.image {
  width: 100%;
}
.title {
  font-size: 40px;
}
.heading {
  @include flex(space-between);
  margin-bottom: 70px;
}
.html-body /deep/ {
  h1,h2,h3,h4,h5,h6 {
    font-weight: bold;
    line-height: 1.5;
    font-feature-settings: "palt";
    margin-top: 2.2em;
    margin-bottom: 2.4rem;
    cursor: pointer;
    position: relative
  }

  h1 a,h2 a,h3 a,h4 a,h5 a,h6 a {
    text-decoration: none
  }

  h1 .fa-link,h2 .fa-link,h3 .fa-link,h4 .fa-link,h5 .fa-link,h6 .fa-link {
    display: none;
    color: #999;
    padding: 12px 8px 4px
  }

  h1 .fa-link:hover,h2 .fa-link:hover,h3 .fa-link:hover,h4 .fa-link:hover,h5 .fa-link:hover,h6 .fa-link:hover {
    color: #4aac00
  }

  h1:hover .fa-link,h2:hover .fa-link,h3:hover .fa-link,h4:hover .fa-link,h5:hover .fa-link,h6:hover .fa-link {
    display: block;
    position: absolute;
    top: 5px;
    left: -28px;
    font-size: 0.6em
  }

  h1>.fragment,h2>.fragment,h3>.fragment,h4>.fragment,h5>.fragment,h6>.fragment {
    position: relative;
    display: block;
    top: -1.5em
  }

  h1 {
    font-size: 1.6em;
    border-bottom: 1px solid #928484;
    padding-bottom: 0.1em
  }

  @media (max-width: 480px) {
    h1 {
        font-size:1.7em
    }
  }

  h2 {
      font-size: 1.3em;
      border-bottom: 1px solid #928484;
      padding-bottom: 0.1em
  }

  @media (max-width: 480px) {
    h2 {
        font-size:1.5em
    }
  }

  h3 {
      font-size: 1.1em
  }

  @media (max-width: 480px) {
    h3 {
        font-size:1.3em
    }
  }

  h4 {
    font-size: 1em
  }

  h5 {
    font-size: 1em
  }

  h6 {
    font-size: 1em
  }

  p {
    line-height: 1.9
  }

  p+p {
    margin-top: 1.5em
  }

  code {
    background-color: #eee;
    color: #333;
    padding: 0.1em 0.4em;
    font-family: "SFMono-Regular",Consolas,"Liberation Mono",Menlo,Courier,monospace
  }

  code .inline-code-color {
    border-radius: 3px;
    border: 1px solid #ddd;
    display: inline-block;
    height: 0.8em;
    margin-left: 4px;
    vertical-align: middle;
    width: 0.8em
  }

  strong {
    font-weight: bold
  }

  em {
    font-style: italic
  }

  del {
    text-decoration: line-through
  }

  a {
    color: #EE817B;
  }

  a:visited {
    color: #EE817B;
  }

  blockquote {
    border-left: 5px solid #ddd;
    color: #777;
    padding: 1em;
    padding-right: 0;
    margin: 1.5em 0
  }

  blockquote .code-frame {
    margin: 1.5em -0.5em;
    padding: 1em 0.5em
  }

  blockquote>ul,blockquote>ol {
    margin-top: 0
  }

  ul,ol {
    padding-left: 1.5em;
    margin: 1.5em 0;
    line-height: 1.9
  }

  ul p,ol p {
    margin: 1em 0
  }

  ul {
    list-style-type: disc
  }

  ul ul {
    list-style-type: circle;
    margin: 0
  }

  ul ul ul {
    list-style-type: square
  }

  ol {
    list-style-type: decimal
  }

  ol ol {
    margin: 0
  }

  img {
    margin: 1.5em 0;
    max-width: 100%
  }

  img.emoji {
    margin: 0
  }

}
</style>
