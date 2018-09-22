<template>
  <div class="discovery">
        <span class="condition" @click="showCityPicker">条件筛选</span>
        <mp-search
          @confirm="onSearchConfirm"
          @change="onSearchChange"
        />
        <!-- <mpvue-city-picker ref="mpvueCityPicker" :pickerValueDefault="pickerValueDefault" @onChange="onChange" @onCancel="onCancel" @onConfirm="onConfirm"></mpvue-city-picker> -->
        <section class="dis_container">
        <demand/>
        <demand/>
        <demand/>
        </section>
    
    <!-- <mp-picker
      v-model="mValue"
      :range="mArray"
      @change="onpickerchange"
      multiple
    >
      <button type="default">多列选择器</button>
    </mp-picker> -->
    <!-- <picker
      mode="multiSelector"
      @change="onpickerChange"
      @columnchange="oncolumnchange"
      :value="index"
      :range="range"
    >
      <slot />
    </picker> -->
    <!-- <choose><button type="default">多列</button></choose> -->
    <vuePicker ref="mpvueCityPicker" 
      :pickerValueDefault="pickerValueDefault" 
      @onChange="onChange" 
      @onCancel="onCancel" 
      @onConfirm="onConfirm">
    </vuePicker>

    <vue-tab-bar
      @fetch-index="clickIndexNav"
      :selectNavIndex="tabbar.selectNavIndex"
    >
    </vue-tab-bar>  
  </div>
</template>

<script>
import MpSearch from 'mp-weui/packages/search'
// import MpPicker from 'mp-weui/packages/picker'
import vueTabBar from '@/components/vueTabBar'
// import choose from '@/components/choose'
import vuePicker from '@/components/vuePicker'
import demand from '@/components/demand'
// import mpvueCityPicker from 'mpvue-citypicker'
// Use Vuex
// import store from './store'

// <p>
//       <button @click="increment">+</button>
//       <button @click="decrement">-</button>
//     </p>

export default {
  data () {
    return {
      pickerValueDefault: [0, 0, 0],
      tabbar: {
        selectNavIndex: 1
      },
      array1: ['四川', '陕西'],
      mArray: [['四川', '陕西'], ['成都', '西安'], ['武侯', '长安']],
      mValue: ['陕西', '西安', '长安']
    }
  },
  components: {
    MpSearch,
    vueTabBar,
    // MpPicker,
    // choose,
    vuePicker,
    demand
    // mpvueCityPicker
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
    showCityPicker () {
      this.$refs.mpvueCityPicker.show()
    },
    onChange (e) {
      console.log(e)
    },
    onCancel (e) {
      console.log(e)
    },
    onConfirm (e) {
      console.log(e)
    },
    clickIndexNav () {

    },
    onSearchConfirm () {

    },
    onSearchChange () {

    },
    onpickerchange (e) {
      // const value = this.getValue(e.target.value);

      // this.$emit('change', value);
      // this.$emit('input', value);

      console.log(e)
    },
    oncolumnchange (e) {

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
.discovery .weui-search-bar{
  margin-left:80px;
}
.discovery .condition{
  float: left;
  background: none;
  border: none;
  width: 60px;
  font-size: 14px;
  height:46px;
  line-height:46px;
  background: #EFEFF4;
  border-top:1rpx solid #D7D6DC;
  border-bottom:1rpx solid #D7D6DC;
  text-align: center;
}
.discovery .dis_container{
  padding-left: 12px;
  padding-right: 12px;
}
</style>
