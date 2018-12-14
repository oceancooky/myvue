<template>
  <div id="app">
    <drawer width="200px;" :show.sync="drawerShow" :show-mode="showMode" :drawer-style="{'background-color':'#35495e', width: '200px'}">
      <div slot="drawer">
        aa
      </div>
      <!-- rourer-view 作为默认插槽内容 -->
      <view-box ref="viewBox">
        <div class='nav_bar' @click="drawerShow = !drawerShow">
          <x-icon type="navicon" size="35" style="fill:#fff;position:relative;"></x-icon>
        </div>
        <router-view></router-view>
      </view-box>
    </drawer>
  </div>
</template>
<script>
import { Drawer,ViewBox } from 'vux'
export default {
  name: 'App',
  data() {
    return {
      drawerShow: false,
      showMode: 'push'
    }
  },
  components: {
    Drawer,
    ViewBox
  },
  methods: {

  }
}

</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%
}

.test-fade-enter-active,
.test-fade-leave-active {
  transition: opacity .5s;
}

.test-fade-enter,
.test-fade-leave-to

/* .fade-leave-active below version 2.1.8 */
  {
  opacity: 0;
}

.nav_bar {
  position: fixed;
  top: 20px;
  left: 20px;
  width: 35px;
  height: 35px;
}

</style>
