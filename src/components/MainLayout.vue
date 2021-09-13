<template>
  <div id="app">
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
.image {
  display: inline-block;
  vertical-align: middle;
  width: 100%;
}
</style>
