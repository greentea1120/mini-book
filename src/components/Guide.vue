<template>
  <transition name="fade">
    <div class="guide" v-show="showGuide">
      <p class="title">花朵,点击左半边上一页,右半边下一页,中间是菜单~~~</p>
      <div class="guide-wrapper">
        <div class="left">上一页</div>
        <div class="middle">菜单</div>
        <div class="right">下一页</div>
      </div>
      <div class="btn" @click="close">我知道了</div>
    </div>
  </transition>
</template>

<script type="text/ecmascript-6">
import Dialog from 'vant/lib/dialog'
import 'vant/lib/dialog/style'
import Toast from 'vant/lib/toast'
import 'vant/lib/toast/style'

export default {
  data() {
    return {
      showGuide: true
    }
  },
  methods: {
    close() {
      this.showGuide = false
      !localStorage.close && this.askYou()
    },
    askYou() {
      Dialog.confirm({
        title: '嘿嘿嘿,问个问题',
        message: '你喜欢我不~~~',
        cancelButtonText: '不喜欢',
        confirmButtonText: '喜欢'
      }).then(() => {
        Toast('开心~')
        localStorage.close = 'flower'
      }).catch(() => {
        Toast({
          message: '- -...我是不会放弃的!',
          duration: 1000
        })
        setTimeout(() => {
          this.askYou()
        }, 3000);
      });
    }
  },
  components: {

  }
}
</script>

<style scoped lang="scss" rel="stylesheet/stylus">
@import '../assets/styles/global';

.guide {
  position: absolute;
  z-index: 199;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, .4);
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  .title {
    font-size: px2rem(14);
    text-align: center;
  }
  .guide-wrapper {
    width: 100%;
    display: flex;
    color: #fff;
    font-size: px2rem(14);
    text-align: center;
    .left,
    .right {
      flex: 0 0 px2rem(100);
    }
    .middle {
      flex: 1;
    }
  }
  .btn {
    width: px2rem(80);
    font-size: px2rem(14);
    padding: px2rem(10) px2rem(20);
    background: #f20d0d;
    border-radius: px2rem(5);
    text-align: center;
  }
}
</style>
