<template>
  <div>
    <TheHeader />

    <div class="body">
      <div class="content">
        <nuxt />
      </div>
      <div class="sidebar">
        <TheSidebar />
      </div>
    </div>

    <TheFooter />
  </div>
</template>

<script>
import Vue from 'vue'
import TheHeader from '~/components/common/TheHeader'
import TheFooter from '~/components/common/TheFooter'
import TheSidebar from '~/components/common/TheSidebar'

export default Vue.extend({
  components: {
    TheHeader,
    TheFooter,
    TheSidebar
  }
})
</script>

<style lang="scss" scoped>

.body {
  max-width: $pc-width;
  margin: auto;
  @include flex(space-between);
  align-items: flex-start;
}

.content {
  @include mq(desktop) {
    width: 610px;
    flex-shrink: 0;
  }
  
}

.sidebar {
  @include mq(desktop) {
    top: 0;
    width: 290px;
    flex-shrink: 0;
    height: 100%;
    position: sticky;
  }
}

/* .button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
} */
</style>
