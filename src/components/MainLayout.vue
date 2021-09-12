<template>
  <div id="app">
    <Header />
    <ul class="images">
      <li v-for="(image, index) in images" :key="index">
        <img :src="image.urls.small" :alt="image.alt_description" class="image" />
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '@/components/Header.vue'
import axios from 'axios'
import datas from '@/assets/data/couples.json'

export default Vue.extend({
  name: 'Main',
  components: {
    Header,
  },
  data () {
    return {
      images: datas,
      search: 'spring',
      client_id: 'qPZTUxnvzIcggSG3yugWxx45eX4x5dqrJlnGoeCEMbs',
    }
  },
  methods: {
    searchUnsplash () {
      this.images = []
      axios.get(`https://api.unsplash.com/search/photos?client_id=${this.client_id}&query=${this.search}&per_page=30`, {
      }).then(response => {
        this.images = response.data.results
      }).catch(() => {
        this.images = []
      })
    }
  }
})
</script>

<style lang="scss" scoped>
.image {
  display: inline-block;
  vertical-align: middle;
  width: 100%;
}
</style>
