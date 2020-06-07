<template>
  <div class="sidebar">
    <div class="categoory">
      <section class="category_section">
        <img class="category-image" src="~/assets/image/category-banner-01.png" alt="">
        <div class="category-body">
          <h3>#フロントエンド の記事一覧</h3>
          <p>フロントエンドの技術に関する記事です。</p>
        </div>
      </section>
      <section class="category_section">
        <img class="category-image" src="~/assets/image/category-banner-02.png" alt="">
        <div class="category-body">
          <h3>#バックエンド の記事一覧</h3>
          <p>バックエンドの技術に関する記事です。</p>
        </div>
      </section>
      <section class="category_section">
        <img class="category-image" src="~/assets/image/category-banner-03.png" alt="">
        <div class="category-body">
          <h3>#コミュニティ の記事一覧</h3>
          <p>同世代エンジニアコミュニティに関する記事です。イベントやコミュニティの活動に関する記事を投稿します。</p>
        </div>
      </section>
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
  }

  .category-image {
    width: 100%;
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
