<template>
  <!-- <div id="app" class="width100 height100">
        <transition name="left">
          </router-view  class='poAbsolute'><router-view/>
        </transition>
  </div> -->
    <div id="app" class="width100 height100">
       <transition :name="($route.path !== '/' || !$store.state.isForward) ? 'left' : ''">
        <router-view class='poAbsolute'></router-view>
      </transition>
    </div>
</template>



<style lang="less">
@import "~vux/src/styles/reset.less";
/* 开始过渡阶段,动画出去阶段 */

.left-enter-active,
.left-leave-active {
  transition: all 0.5s;
  opacity: 1;
}

/* 进入开始 */

.left-enter {
  transform: translate3D(100%, 0, 0);
  opacity: 1;
}

/* 出去终点 */

.left-leave-active {
  transform: translateX(-100%);
  opacity: 1;
}
</style>
<script>
export default {
  name: "App"
};
import "./assets/css/app.css";
</script>