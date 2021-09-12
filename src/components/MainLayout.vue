<template>
  <div id="app">
    <Header />
    <h1 class="heading">𝙇𝙤𝙪𝙞𝙨𝙩𝙖𝙜𝙧𝙖𝙢</h1>
    <div class="container">
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
      client_id: 'qPZTUxnvzIcggSG3yugWxx45eX4x5dqrJlnGoeCEMbs',
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
</style>
