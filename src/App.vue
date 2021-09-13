<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<style lang="scss">
.fade-enter-active,
.fade-leave-active { transition: opacity .1s }
.fade-enter,
.fade-leave-to { opacity: 0 }

@import '@/../colony-vue/src/assets/scss/reset.scss';
@import '@/assets/scss/variable.scss';
@import '@/assets/scss/modal.scss';
@import '@/assets/scss/reset.scss';
@import '@/assets/scss/modal.scss';
</style>
