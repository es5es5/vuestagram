<template>
  <div id="app">
    <div class="container">
      <!-- <div class="button-wrapper">
        <button>dd</button>
        <button class="btn" @click="searchUnsplash('Autumn')">Autumn</button>
      </div> -->
      <stack
        :column-min-width="300"
        :gutter-width="15"
        :gutter-height="15"
        monitor-images-loaded
      >
        <stack-item
          v-for="(image, i) in images"
          :key="i"
          style="transition: transform 300ms"
        >
          <img :src="image.urls.small" :alt="image.alt_description" />
        </stack-item>
      </stack>
    </div>
  </div>
</template>

<script lang="js">
import Vue from 'vue'
import axios from 'axios'
import { Stack, StackItem } from 'vue-stack-grid'
import autumn from '@/assets/data/autumn.json'

export default Vue.extend({
  name: 'Main',
  components: {
    Stack,
    StackItem,
  },
  data () {
    return {
      images: autumn,
      // client_id: 'qPZTUxnvzIcggSG3yugWxx45eX4x5dqrJlnGoeCEMbs',
      client_id: '',
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
    searchUnsplash (topic) {
      this.images = []
      axios.get(`https://api.unsplash.com/search/photos?client_id=${this.client_id}&query=${topic}`, {
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
</style>
