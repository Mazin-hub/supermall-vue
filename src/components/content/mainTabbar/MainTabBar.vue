<template>
  <tab-bar>
      <tab-bar-item path="/home" activeColor="blue">
        <template v-slot:item-icon>
          <img src="~assets/img/tabbar/home.svg">
        </template>
        <template v-slot:item-icon-active>
          <img src="~assets/img/tabbar/home_active.svg">
        </template>
        <template v-slot:item-text>
           <div>首页</div>
        </template>
      </tab-bar-item>

      <tab-bar-item path="/category" activeColor="blue">
        <template v-slot:item-icon>
          <img src="~assets/img/tabbar/category.svg" >

        </template>
        <template v-slot:item-icon-active>
          <img src="~assets/img/tabbar/category_active.svg">
        </template>
        <template v-slot:item-text>
          <div>分类</div>
        </template>
      </tab-bar-item>

      <tab-bar-item  path="/cart" activeColor="blue">
        <template v-slot:item-icon>
          <img src="~assets/img/tabbar/cart.svg" >
        </template>
        <template v-slot:item-icon-active>
          <img src="~assets/img/tabbar/cart_active.svg">
        </template>
        <template v-slot:item-text>
          <div>购物车</div>
        </template>
      </tab-bar-item>

      <tab-bar-item path="/profile" activeColor="blue">
        <template v-slot:item-icon>
          <img src="~assets/img/tabbar/profile.svg" >
          <div>我的</div>
        </template>
        <template v-slot:item-icon-active>
          <img src="~assets/img/tabbar/profile_active.svg">
        </template>
        <template v-slot:item-text>
          <div>我的</div>
        </template>
      </tab-bar-item>

    </tab-bar>

</template>

<script>
// 路径取别名，在 build/webpack.base.conf.js 的 resolve 的 alias
import TabBar from 'components/common/tabbar/TabBar'
import TabBarItem from 'components/common/tabbar/TabBarItem'

export default {
  components:{
    TabBar,
    TabBarItem
  }
}
</script>

<style>
  /* @import 'assets/css/base.css'; */
</style>
