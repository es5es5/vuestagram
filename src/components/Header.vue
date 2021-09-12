<template>
  <div>
    <div class="heading_wrap">
      <h1 class="heading">𝙇𝙤𝙪𝙞𝙨𝙩𝙖𝙜𝙧𝙖𝙢</h1>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'Header'
})
</script>

<style lang="scss" scoped>
.heading_wrap {
  padding: 10px 16px;

  .heading {
    display: inline-block;
    vertical-align: middle;
    letter-spacing: -3px;
    line-height: 30px;
    font-size: 30px;
  }
}
</style>
