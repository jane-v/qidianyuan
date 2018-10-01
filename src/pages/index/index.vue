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
    <section class="notice">
      <img class="notice_img" src="/static/images/img_notice.png" />
      <swiper class="swiper_msg" vertical="true" autoplay="true" circular="true" interval="2000">
        <div v-for="(item, index) in msgList" :key="index">
          <!-- <navigator url="/pages/index/index?title={{item.url}}" open-type="navigate">
            <swiper-item>
            <view class="swiper_item">{{item.title}}</view>
            </swiper-item>
          </navigator> -->
          <swiper-item>
            <span class="swipermsg_item">{{item.title}}</span>
          </swiper-item>
        </div>
      </swiper>
    </section>
    <ul class="li-list">
      <li @click="openurl('http://www.baidu.com')"></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
    <!-- <a href="/pages/index/main" class="home">去往首页</a> -->
    <section class="business">
      <p class="title">行业资源选择</p>
      <p><img class="busi_img" src="/static/images/img_unlock.png" />已解锁行业资源</p>
      <ul>
        <li class="selected">打发首付是</li>
        <li class="selected">水电费</li>
        <li class="selected">滴滴</li>
        <li class="selected">阿斯蒂芬</li>
      </ul>
      <p><img class="busi_img" src="/static/images/img_lock.png" />未解锁行业资源</p>
      <ul>
        <li>打发首付是</li>
        <li>水电费</li>
        <li>滴滴</li>
        <li >阿斯蒂芬</li>
      </ul>
    </section>
    <vue-tab-bar
      @fetch-index="clickIndexNav"
      :selectNavIndex="tabbar.selectNavIndex"
      :needButton="tabbar.needButton"
      :handButton="tabbar.handButton"
      :btnText="tabbar.btnText">
    </vue-tab-bar>  
  </div>
</template>

<script>
import MpSearch from 'mp-weui/packages/search'
import vueTabBar from '@/components/vueTabBar'
// Use Vuex
// import store from './store'

// <p>
//       <button @click="increment">+</button>
//       <button @click="decrement">-</button>
//     </p>

export default {
  data () {
    return {
      tabbar: {
        selectNavIndex: 0
      },
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
      },
      msgList: [
        { url: '', title: '多地首套房贷利率上浮 热点城市渐迎零折扣时代' },
        { url: '', title: '悦如公寓三周年生日趴邀你免费吃喝欢唱' },
        { url: '', title: '你想和一群有志青年一起过生日嘛？' }
      ]
    }
  },
  components: {
    MpSearch,
    vueTabBar
  },
  computed: {
    // count () {
    //   return store.state.count
    // }
  },
  onShow () {
    console.log('onshow')
    wx.hideTabBar()
  },
  onLoad () {
    // console.log('onLoad')
    // wx.hideTabBar()
  },
  methods: {
    clickIndexNav () {

    },
    onSearchConfirm () {

    },
    onSearchChange () {

    },
    swiperChange (e) {
      // console.log('第' + e.mp.detail.current + '张轮播图发生了滑动')
    },
    animationfinish (e) {
      // console.log('第' + e.mp.detail.current + '张轮播图滑动结束')
    },
    openurl (url) {
      // wx.navigateTo({url: '/pages/webview?url=' + encodeURIComponent(url)})
      wx.navigateTo({
        url: '/pages/webview/main'
      }

      )
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

<style lang="less" scoped>
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
  padding-bottom:40px;
}
swiper{
  margin: 12px 12px 0px;
  border:rgba(204, 204, 204, 1) solid 1px;
  border-radius: 6px;
}
.li-list{
  padding:0px 13px;
  display: flex;
  justify-content:space-between;
  height: 74px;
}
.li-list li{
  width: 74px;
  background:#d8d8d8;
  border-radius:6px;
}
.business{
  padding: 13px;
  p{
    font-size:14px;
    color:#666666;
    line-height:30px;
    text-align:left;
    
    &.title{
      text-align: left;
      color:#1a1a1a;
      font-size:20px;
    }
    .busi_img{
      width: 12px;
      height: 14px;
      vertical-align:text-top;
      margin-right: 3px;
    }
  }
}
.business ul{
  display: flex;
  align-content:space-around;
  flex-wrap:wrap;
  justify-content:space-between;
  margin-top:-10px;
  margin-bottom:15px;
}
.business li{
  border:1px solid #e6e6e6;
  border-radius:20.5px;
  margin-top:12px;
  font-size: 14px;
  line-height: 40px;
  font-size:14px;
  height: 40px;
  width: 31%;
  &.selected{
    background:#7a87ff;
    border-radius:20.5px;
    color:#fff;
  }
}
.notice{
  width: 100%;
  height: 50px;
  margin-top:-10px; 
}
.swiper_msg{
  font-size:14px;
  color:#000000;
  line-height:50px;
  text-align: left;
  height: 50px;
  border:none;
  margin-left:35px;
  .swiper-item{
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    letter-spacing: 2px;
  }
  .swipermsg_item{
    margin-left: 5px;
  }
  img{
    height: 12px;
    width: 16px;
  }
}
.notice_img{
  height: 12px;
  width: 16px;
  float: left;
  margin-left: 16px;
  margin-top: 19px;
}
</style>