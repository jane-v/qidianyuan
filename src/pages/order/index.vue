<template>
  <div class="order">
        <mp-search
          @confirm="onSearchConfirm"
          @change="onSearchChange"
        />
        <section class="demandlist">
          <demand/>
          <demand/>
          
          
        </section>
        <p>---------我是有底线的----------</p>

    <vue-tab-bar
      @fetch-index="clickIndexNav"
      :selectNavIndex="tabbar.selectNavIndex"
    >
    </vue-tab-bar>  
  </div>
</template>

<script>
import MpSearch from 'mp-weui/packages/search'
import vueTabBar from '@/components/vueTabBar'
import demand from '@/components/demand'

export default {
  data () {
    return {
      tabbar: {
        selectNavIndex: 1
      }
    }
  },
  components: {
    MpSearch,
    vueTabBar,
    demand
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
    onSearchConfirm () {

    },
    onSearchChange () {

    }
  }
}
</script>

<style  lang="less" scoped>
.order {
  padding-bottom:20px;
  .demandlist{
    background: grey;
    padding-bottom:0px;
  }
  p{
    font-size: 12px;
    color: grey;
    text-align: center;
    background: #fff;
  }
}
</style>
