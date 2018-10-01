<template>
  <div class="mine">
    <my-card></my-card>
    <ul class="jumpmine">
      <li @click="jumpmine()">
        <span class="num">8</span>
        <span>我发布的</span>
      </li>
      <li class="border">
        <span class="num">100</span>
        <span>已匹配的</span>
      </li>
      <li>
        <span class="num">223</span>
        <span>我收藏的</span>
      </li>
    </ul>
    <jump-line 
      lable="我的会员"
      border = "true"
      imgsrc = '/static/images/img_vip.png'
      margin_top = "true"
    ></jump-line>
    <!-- <jump-line 
      lable="我的消息"
      border = "true"
      imgsrc = '/static/images/img_message.png'
    ></jump-line> -->
    <jump-line 
      lable="我的收藏"
      border = "true"
      imgsrc = '/static/images/img_collect.png'
    ></jump-line>
    <jump-line 
      lable="身份认证"
      border = "true"
      imgsrc = '/static/images/img_certify.png'
    ></jump-line>
    <jump-line 
      lable="个人海报"
      imgsrc = '/static/images/img_haibao.png'
    ></jump-line>
    <jump-line 
      lable="关于我们"
      border = "true"
      margin_top = "true"
      imgsrc = '/static/images/img_about.png'
    ></jump-line>
    <jump-line 
      lable="意见反馈"
      imgsrc = '/static/images/img_contact.jpg'
    ></jump-line>
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
import vueTabBar from '@/components/vueTabBar'
import myCard from '@/components/myCard'
import jumpLine from '@/components/jumpLine'

export default {
  data () {
    return {
      tabbar: {
        selectNavIndex: 4
      }
    }
  },
  components: {
    vueTabBar,
    myCard,
    jumpLine
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
    jumpmine () {

    }
  }
}
</script>

<style lang="less" scoped>
.mine{
  background: #f5f5f5;
  padding-bottom:60px;
  .jumpmine{
    background: #ffffff;
    display: flex;
    align-content:space-around;
    flex-wrap:wrap;
    justify-content:space-between;
    height: 73px;
    li{
      width: 33.33%;
      text-align:center;
      span{
        font-size:12px;
        color:#666666;
        display: block;
        &.num{
          font-size:20px;
          color:#000000;
          margin-top:10px;
        }
      }
    }
  }
}
</style>
