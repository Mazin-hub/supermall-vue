<template>
  <div id='home'>
    <nav-bar class='home-nav'>
      <template v-slot:center>
        <div>购物街</div>
      </template>
    </nav-bar>
    <home-swipers :banners='banners'/>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import {getHomeMultidata} from 'network/home'
import HomeSwipers from './childComps/HomeSwipers'

export default {
  name: 'Home',
  components: {
    NavBar,
    HomeSwipers
  },
  data() {
    return {
      banners:[],
      recommends:[]
    }
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res);
      this.banners = res.data.banner.list
      this.recommends = res.data.recommend.list
    })
  }
}
</script>

<style>
  .home-nav{
    background-color: #ff8198;
    color: white
  }
</style>
