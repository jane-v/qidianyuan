<template>
  <div class="home">
    <mp-search
      @confirm="onSearchConfirm"
      @change="onSearchChange"
    />
    <swiper :indicator-dots="swipers.indicatorDots" :autoplay="swipers.autoplay" :interval="swipers.interval" :duration="swipers.duration" :circular="swipers.circular" @change="swiperChange" @animationfinish="animationfinish">
      <div v-for="(item, index) in swipers.imgUrls" :key="index">
        <swiper-item>
          <image :src="item" class="slide-image" />
        </swiper-item>
      </div>
    </swiper>
    
    <p>
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </p>

    <a href="/pages/index/main" class="home">去往首页</a>
  </div>
</template>

<script>
import MpSearch from 'mp-weui/packages/search'
// Use Vuex
// import store from './store'

export default {
  data () {
    return {
      swipers: {
        indicatorDots: true,
        autoplay: true,
        interval: 5000,
        duration: 900,
        circular: true,
        imgUrls: [
          'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg'
        ]
      }
    }
  },
  components: {
    MpSearch
  },
  computed: {
    // count () {
    //   return store.state.count
    // }
  },
  methods: {
    onSearchConfirm () {

    },
    onSearchChange () {

    },
    swiperChange (e) {
      console.log('第' + e.mp.detail.current + '张轮播图发生了滑动')
    },
    animationfinish (e) {
      console.log('第' + e.mp.detail.current + '张轮播图滑动结束')
    }
    // increment () {
    //   store.commit('increment')
    // },
    // decrement () {
    //   store.commit('decrement')
    // }
  }
}
</script>

<style scoped>
.counter-warp {
  display: inline-block;
  margin: 100px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
.home {
  text-align: center;
  margin-top: 0px;
}
</style>
