<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive">
      <slot name="item-icon"></slot>
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <!-- 动态绑定类不起效 是因为插槽会被直接替换所以需要在插槽外封装一层div 把类的动态绑定放在外面的类中 当插槽被替换后 动态绑定类仍然是生效的 -->
    <!-- <slot :class="{active: isActive}" name="item-text"></slot> -->
    <div :style="activeStyle">
      <slot name="item-text"></slot>
    </div>
    <!-- <img src="../../assets/img/tabbar/shouye.png" alt />
    <div>首页</div>-->
  </div>
  <!-- <div class="tab-bar-item">
        <img src="../../assets/img/tabbar/jifenzhongxin.png" alt="">
        分类</div>
      <div class="tab-bar-item">
        <img src="../../assets/img/tabbar/gwc.png" alt="">
        购物车</div>
      <div class="tab-bar-item">
        <img src="../../assets/img/tabbar/grzx.png" alt="">
  我的</div>-->
</template>

<script>
export default {
  name: "TabBarItem",
  props:{
    path:String,
    activeColor:{
      type: String,
      default: 'red'
    }
  },
  computed:{
    isActive(){
      // /home -> item1(/home) =true
      // /home -> item1(/catrgory) = false
      // indexOf找不到某个值返回-1
      return this.$route.path.indexOf(this.path) !== -1
    },
    activeStyle(){
      return this.isActive ? {color:this.activeColor} : {}
    }
  },
  data() {
    return {
      // isActive: true,
    };
  },
  methods:{
    itemClick(){
      // console.log('itemclick');
      this.$router.replace(this.path)
    }
  }
};
</script>

<style>
.tab-bar-item {
  flex: 1;
  text-align: center;
  height: 49px;
  font-size: 14px;
}
.tab-bar-item img {
  /* display: block;
    margin-left: 18px; */
  height: 24px;
}
/* .active {
  color: red;
} */
</style>