<template>
  <div class="header">
    <div class="inner">
      <img class="logo" src="~/assets/image/icon.png" alt="エンジニアのひとりごと">
    </div>
  </div>
</template>
<style scoped lang="scss">

  .header {
    padding: 20px 0;
  }

  .inner {
    @include contentWidth();
    text-align: center;
  }

  .logo {
    width: 400px;
  }

</style>
