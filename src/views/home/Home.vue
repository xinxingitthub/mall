<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recomend-view :recommends="recommends"></recomend-view>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";

  import {getHomeMultidata} from "network/home";
  import HomeSwiper from "./childComps/HomeSwiper";
  import RecomendView from "./childComps/RecomendView";

  export default {
    name: "Home",
    data() {
      return {
        banners: [],
        recommends: []
      }
    },
    components: {
      RecomendView,
      NavBar,
      HomeSwiper
    },
    created() {
      getHomeMultidata().then(res => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      })
    }
  }
</script>

<style scoped>

  .home-nav {
    background-color: var(--color-tint);
    color: #eeeeee;
  }
</style>
