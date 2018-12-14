<template>
  <div class="main">
    <home :is="currentTab" keep-alive></home>
    <div class="index_tabbar">
      <tabbar @on-index-change="onIndexChange">
        <tabbar-item selected>
          <img slot="icon" src="../assets/tabbar/bar_home_nor.png">
          <img slot="icon-active" src="../assets/tabbar/bar_home_set.png">
          <span slot="label">Wechat</span>
        </tabbar-item>
        <tabbar-item>
          <img slot="icon" src="../assets/tabbar/bar_shop_nor.png">
          <img slot="icon-active" src="../assets/tabbar/bar_shop_set.png">
          <span slot="label">Message</span>
        </tabbar-item>
        <tabbar-item>
          <img slot="icon" src="../assets/tabbar/bar_zone_nor.png">
          <img slot="icon-active" src="../assets/tabbar/bar_zone_set.png">
          <span slot="label">Explore</span>
        </tabbar-item>
        <tabbar-item>
          <img slot="icon" src="../assets/tabbar/bar_mine_nor.png">
          <img slot="icon-active" src="../assets/tabbar/bar_mine_set.png">
          <span slot="label">News</span>
        </tabbar-item>
      </tabbar>
    </div>
  </div>
</template>
<script>
import { Tabbar, TabbarItem } from 'vux';
import home from '../../src/components/home';
import mine from '../../src/components/mine';
import shop from '../../src/components/shop';
import zone from '../../src/components/zone';
export default {
  name: 'index',
  components: {
    Tabbar,
    TabbarItem,
    home,
    mine,
    shop,
    zone
  },
  data() {
    return {
      select: "home",
      path: ['home', 'shop', 'zone', 'mine'],
      currentTab: 'home'
    }
  },

  methods: {
    onIndexChange(index) {
      this.currentTab = this.path[index]
    }
  }
}

</script>
<style>
.index_tabbar {
  width: 100%;
  position: fixed;
  bottom: 0;
  left: 0
}

</style>
