<template>
  <div class="article-card">
    <nuxt-link :to="'/article/' + article.id" class="card_link" :class="{'first--link': index===0}">
      <img class="card_image" v-if="index === 0" :src="article.Image.url + '?fit=max&w=610&h=320'">
      <img class="card_image" v-else :src="article.Image.url + '?fit=max&w=104&h=104'">
      <div class="card_body">
        <h2 class="card_title">{{ article.title }}</h2>
        <div class="card_category">{{ article.category.name }}</div>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    article: {
      required: true,
      type: Array
    },
    index: {
      type: Number
    }
  }
}
</script>

<style scoped lang="scss">

  .article-card {
    padding: 20px;
    transition: background-color 0.3s;
    + .article-card {
      margin-top: 40px;
      position: relative;
      &:before {
        content: '';
        background-color: #e2e2e2;
        width: calc(100% - 40px);
        height: 1px;
        display: block;
        position: absolute;
        top: -20px;
      }
    }
    &:hover {
      background-color: #f5f5f5;
    }
  }

  .card_link {
    @include flex(space-between);
     &.first--link {
      display: block;
    }
  }

  .card_image {
    order: 2;
    width: 104px;
    height: 104px;
    border-radius: 10px;
    object-fit: cover;
    .first--link & {
      width: 100%;
      height: 100%;
      margin-bottom: 10px;
      border-radius: 0;
    }
  }
  .card_title {
    font-size: 22px;
    margin-bottom: 8px;
    font-weight: 700;
    line-height: 1.5;
    letter-spacing: .04em;
  }
  .card_category {
    font-size: 12px;
    color: #9f9f9f;
  }

</style>
