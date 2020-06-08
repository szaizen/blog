<template>
  <div class="sidebar">
    <div class="categoory">
      <nuxt-link to="/category/r16d9ngcp" class="category_section">
        <img class="category-image" src="~/assets/image/category-banner-01.png" alt="">
        <div class="category-body">
          <h3>#フロントエンド の記事一覧</h3>
          <p>フロントエンドの技術に関する記事です。</p>
        </div>
      </nuxt-link>
      <nuxt-link to="/category/ookdtbqud" class="category_section">
        <img class="category-image" src="~/assets/image/category-banner-02.png" alt="">
        <div class="category-body">
          <h3>#バックエンド の記事一覧</h3>
          <p>バックエンドの技術に関する記事です。</p>
        </div>
      </nuxt-link>
      <nuxt-link to="/category/cjvcdkjer" class="category_section">
        <img class="category-image" src="~/assets/image/category-banner-03.png" alt="">
        <div class="category-body">
          <h3>#コミュニティ の記事一覧</h3>
          <p>同世代エンジニアコミュニティに関する記事です。イベントやコミュニティの活動に関する記事を投稿します。</p>
        </div>
      </nuxt-link>
    </div>
  </div>
</template>
<style lang="scss" scoped>

.sidebar {
  padding: 20px 0;
}

.category_section {
  border: 1px solid #e4e4e4;
  margin-bottom: 20px;
  display: block;
  overflow: hidden;
  transition: box-shadow 0.4s;
  &:hover {
    box-shadow: 0px 15px 31.5px 3.5px rgba(0, 0, 0, 0.05);
    .category-image {
      transform: scale(1.1);
    }
  }
}

.category-image {
  width: 100%;
  transition: transform 0.4s;
}

.category-body {
  padding: 20px;
  h3 {
    font-size: 14px;
    margin-bottom: 5px;
  }
  p {
    font-size: 12px;
  }
}

</style>
