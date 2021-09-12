<template>
  <div id="app">
    <Header />
    <h1 class="heading">𝙇𝙤𝙪𝙞𝙨𝙩𝙖𝙜𝙧𝙖𝙢</h1>
    <div class="container">
      <ul class="images">
        <li v-for="(image, index) in images" :key="index">
          <img :src="image.urls.small" :alt="image.alt_description" class="image" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import datas from '@/assets/data/couples.json'

export default Vue.extend({
  name: 'Main',
  data () {
    return {
      images: datas,
      search: 'spring',
      items: [{
        width: 10,
        height: 10,
      }, {
        width: 10,
        height: 10,
      }]
    }
  },
  methods: {
  }
})
</script>

<style lang="scss" scoped>
.heading {
  font-size: 40px;
}

.image {
  display: inline-block;
  vertical-align: middle;
  width: 100%;
}
</style>
