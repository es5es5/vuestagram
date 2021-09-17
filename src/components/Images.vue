<template>
  <ul class="images">
    <viewer
      :options="{
        keyboard: true,
        title: false,
      }"
    >
      <li v-for="(image, index) in images" :key="index">
        <img :src="image.urls.small" :alt="image.alt_description" class="image" />
        <p class="date">2021-05-05 12:12 (Tue)</p>
      </li>
    </viewer>
  </ul>
</template>

<script lang="ts">
import Vue from 'vue'
import datas from '@/assets/data/korean.json'
import axios from 'axios'

export default Vue.extend({
  name: 'Images',
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
.images {
  li {
    position: relative;
  }

  .image {
    display: inline-block;
    vertical-align: middle;
    width: 100%;
  }

  .date {
    position: absolute;
    bottom: 10px;
    right: 10px;
    font-size: 11px;
    color: #eee;
  }
}
</style>
