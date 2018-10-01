<template>
  <section  :class="['jumpline', border ? 'border':'', margin_top ? 'margin_top':'']"  @click="jumphref(jumpaddress)">
    <img :src='imgsrc' />
    <span>{{lable}}</span>
    <img src='/static/images/img_right.png' class="right"/>
  </section>
</template>

<script>
export default {
  data () {
    return {
      lll: '123345'
    }
  },
  props: ['imgsrc', 'lable', 'jumpaddress', 'border', 'margin_top'],
  method: {
    jumphref (url) {
      wx.navigateTo({
        url
      })
    }
  }
}
</script>

<style lang="less" scoped>
.jumpline{
    height: 51px;
    line-height: 51px;
    padding-left: 16px;
    padding-right:16px;
    background: #fff;
    font-size:16px;
    color:#000000;
    &.border{
        border-bottom: #f5f5f5 solid 1px;
    }
    &.margin_top{
        margin-top: 6px;
    }
    img{
        height: 24px;
        width: 24px;
        vertical-align:-10%;
    }
    span{
        margin-left:10px;
    }
    .right{
        float: right;
        width: 9px;
        height: 9px;
        margin-top:20px;
    }
}
</style>
