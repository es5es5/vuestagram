<template>
  <div id="header" :class="[scrolling ? 'scrolling' : '', _propTheme !== '' ? _propTheme : theme]">
    <div class="header_wrap">
      <!-- <img src="@/assets/images/Louistagram-stroke.svg" alt="Louistagram" class="heading"> -->
      <h1 class="heading">𝙇𝙤𝙪𝙞𝙨𝙩𝙖𝙜𝙧𝙖𝙢</h1>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Header',
  data () {
    return {
      scrolling: false,
      theme: '',
    }
  },
  methods: {
  }
})
</script>

<style lang="scss" scoped>
@import '@/../colony-vue/src/assets/scss/variable.scss';
@import '@/assets/scss/variable.scss';

#header {
  @include clearfix;

  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 5000;
  transition: all .3s;

  // height: 60px;
  color: #fff;
  background-color: rgba($primary, 0);
  border-bottom: 1px solid rgba(gray, 0);

  &.reverse {
    background-color: rgba(#F1F2F4, .95);
    border-bottom: 1px solid transparent;
    color: #000;
    border-bottom: 1px solid rgba(gray, .2);
    -webkit-box-shadow: 0px 15px 30px 10px rgba(0,0,0,0.05);
    box-shadow: 0px 15px 30px 10px rgba(0,0,0,0.05);
  }

  &.scrolling {
    background-color: rgba(#F1F2F4, .95);
    border-bottom: 1px solid transparent;
    color: $primary;
    border-bottom: 1px solid rgba($primary, .8);
  }
}

.header_wrap {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin: 0 auto;
  padding: 0 20px;
}

.heading {
  display: inline-block;
  vertical-align: middle;
  letter-spacing: -1px;
  line-height: 60px;
  font-size: 24px;

  &:hover { cursor: pointer; }
}

.user_wrap {
  align-self: center;
  line-height: 60px;

  @media screen and (max-width: 768px) {
    font-size: 15px;
  }
  @media screen and (min-width: 769px) {
    font-size: 20px;
  }

  display: flex;
  justify-content: space-around;
  align-items: baseline;

  &:hover {
    cursor: pointer;
    text-decoration: underline;
  }
  .avatar {
    width: 2em;
    height: 2em;
    border-radius: 50%;
    align-self: center;
    margin-right: .5em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12), 0 2px 10px 0 rgba(34,36,38,.15);
  }

  .userName {
    font-weight: bold;
    align-self: center;
    font-size: 1em
  }
}

.login_wrap {
  @include hover;

  // color: #fff;
  color: #000;
  line-height: 50px;

  .icon {
    line-height: 1.25em;
    vertical-align: middle;
    width: 1.25em;
    height: 1.25em;
    margin-right: .5em;
  }
  .login {
    vertical-align: middle;
    line-height: 1.25em;

    &.scrolling {
      color: #000;
    }
  }
}
// .login {
//   align-self: center;
//   background-color: rgba($success, .95);
// }

</style>
