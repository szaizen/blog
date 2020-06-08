<template>
  <div class="header">
    <div class="inner">
      <nuxt-link to="/">
        <img class="logo" src="~/assets/image/icon.png" alt="エンジニアのひとりごと">
      </nuxt-link>
    </div>
  </div>
</template>
<style scoped lang="scss">

  .header {
    padding: 20px 0;
    border-bottom: 1px solid #dfdfdf;
    margin-bottom: 21px;
  }

  .inner {
    @include contentWidth();
    text-align: center;
  }

  .logo {
    width: 400px;
  }

</style>
