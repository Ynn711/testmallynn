<template>
   <tab-bar>
      <tab-bar-item path='/home' activeColor='blue'>
        <img slot="item-icon" src="~assets/img/tabbar/shouye.png" alt />
        <img slot="item-icon-active" src="~assets/img/tabbar/shouye1.png" alt="">
        <div slot="item-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path='/category'>
        <img slot="item-icon" src="~assets/img/tabbar/jifenzhongxin.png" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/jifenzhongxin1.png" alt="">
        <div slot="item-text">分类</div>
      </tab-bar-item>
      <tab-bar-item path='/cart'>
        <img slot="item-icon" src="~assets/img/tabbar/gwc.png" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/gwcc.png" alt="">
        <div slot="item-text">购物车</div>
      </tab-bar-item>
      <tab-bar-item path='/profile'>
        <img slot="item-icon" src="~assets/img/tabbar/grzx.png" alt="">
        <img slot="item-icon-active" src="~assets/img/tabbar/grzxc.png" alt="">
        <div slot="item-text">我的</div>
      </tab-bar-item>
    </tab-bar>



</template>

<script>
import TabBar from 'components/common/tabbar/TabBar'
import  TabBarItem from 'components/common/tabbar/TabBarItem'
export default {
  name:'MainTabBar',
  components:{
    TabBar,
    TabBarItem
  }
}
</script>

<style>

</style>
