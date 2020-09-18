<template>
  <div class="tab-bar-item" @click="itemclick">
    <div v-if="!isActive"><slot name="item-icon"></slot> <!-- 图标 --></div>
    <div v-else><slot name="item-icon-active"></slot> <!-- 激活图标 --></div>
    <div :style="activeStyle">
      <slot name="item-text"></slot> <!-- 文字, slot 直接被替换，写在 slot标签上的属性可能不起效果 -->
    </div>
  </div>
</template>

<script>
export default {
  name:"TabBarItem",
  props:{
    path:String,
    activeColor:{
      type:String,
      default:'red'
    }
  },
  data(){
    return{
      // isActive: true
    }
  },
  computed:{
    isActive() {
      // 当前激活路由 与 对应传入的 url 相同
      // console.log(this.$route.path === this.path);
      // console.log(this.$route.path.indexOf(this.path) !== -1);
      return this.$route.path === this.path
    },
    activeStyle() {
      return this.isActive ? {color:this.activeColor} : {}
    }
  },
  methods:{
    itemclick() {
      this.$router.replace(this.path)
    }
  }
}
</script>

<style>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 14px;
  }
  .tab-bar-item img{
    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle;
    margin-bottom: 2px;
  }
  /* .active{
  } */
</style>
