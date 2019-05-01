<template>
  <transition name="fade">
    <div class="welcome" v-show="showWelcome">
      <div class="title-wrapper">
        <img src="./flower.svg" class="logo" alt="">
        <p class="title">小花朵阅读器</p>
        <p class="words">4.22 - 至今</p>
      </div>
      <div class="bottom-wrapper">
        <div class="btn" @click="close">开始使用</div>
        <p class="version">beta 0.1.0</p>
      </div>
    </div>
  </transition>
</template>

<script type="text/ecmascript-6">
export default {
  data() {
    return {
      showWelcome: true
    }
  },
  methods: {
    close() {
      this.showWelcome = false
    }
  },
  components: {

  }
}
</script>

<style scoped lang="scss" rel="stylesheet/stylus">
@import '../assets/styles/global';

.welcome {
  position: absolute;
  z-index: 200;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  .title-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    .title {
      color: #333;
      font-size: px2rem(20);
      padding: px2rem(20);
    }
    .words {
      color: #999;
      font-size: px2rem(16);
    }
    .logo {
      width: px2rem(50);;
      height: px2rem(50);;
    }
  }
  .bottom-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .btn {
      width: px2rem(60);
      padding: px2rem(10) px2rem(16);;
      border-radius: px2rem(5);
      font-size: px2rem(14);
      color: #fff;
      background: #4aabff;
    }
    .version {
      margin-top: px2rem(20);
      color: #999;
      font-size: px2rem(14);
    }
  }
}
</style>
