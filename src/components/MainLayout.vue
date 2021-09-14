<template>
  <div id="MainLayout">
    <Header />
    <Images />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '@/components/Header.vue'
import Images from './Images.vue'

export default Vue.extend({
  name: 'Main',
  components: {
    Header,
    Images,
  },
})
</script>

<style lang="scss" scoped>
@media screen and (min-width: 750px) {
  #MainLayout {
    margin: 100px auto;
    width: 375px;
    max-height: 812px;
    overflow-y: scroll;
  }
}
</style>
