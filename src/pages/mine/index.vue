<template>
  <div class="home">
    <ul class="li-list">
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
    <a href="/pages/index/main" class="home">去往首页</a>
    <section class="business">
      <p>资源行业选择</p>
      <ul>
        <li>打发首付是</li>
        <li>水电费</li>
        <li>滴滴</li>
        <li>阿斯蒂芬</li>
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

export default {
  data () {
    return {
      tabbar: {
        selectNavIndex: 4
      }
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
  methods: {

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
swiper{
  margin: 12px;
  border:rgba(204, 204, 204, 1) solid 1px;
  border-radius: 6px;
}
.li-list{
  padding:13px;
  display: flex;
  justify-content:space-between;
  height: 66px;
}
.li-list li{
  border: solid rgba(204, 204, 204, 1) 1px;
  width: 66px;
}
.business{
  padding: 13px;
}
.business p{
  text-align: left;
  color:rgba(144, 129, 222, 1)
}
.business ul{
  display: flex;
  align-content:space-around;
  flex-wrap:wrap;
  justify-content:space-between;
}
.business li{
  background: rgba(229, 229, 229, 1);
  border-radius:4px;
  margin-top:12px;
  font-size: 14px;
  line-height: 30px;
  border:rgba(204, 204, 204, 1) solid 1px;
  height: 30px;
  width: 31%;
}
</style>
