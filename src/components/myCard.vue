<template>
  <section class="minecard">
    <section class="imgcontainer">

    </section>
    <section>
        <h2>用户昵称</h2>
        <p>职位：行政总裁</p>
        <p>公司：源企点国际有限公司</p>
        <p>简介：我是广州十大杰出青年，喜欢我的请关注</p>
        <demand-card type="vip1"></demand-card><demand-card type="renZheng"></demand-card>
    </section>
  </section>
</template>

<script>
import demandCard from '@/components/demandCard'
export default {
  data () {
    return {
      lll: '123345'
    }
  },
  props: ['text'],
  components: {
    demandCard
  }
}
</script>

<style lang="less" scoped>
.minecard{
    padding: 20px 16px 16px;
    position: relative;
    box-shadow:0 0 0 0 #f0f0f0;
    border-bottom: #f5f5f5 solid 1px;
    background: #ffffff;
    h2{
        font-size:20px;
        color:#000000;
        line-height:30px;
        text-align:left;
    }
    p{
        font-size:14px;
        color:#000000;
        line-height:25px;
        text-align:left;
    }
}
.imgcontainer {
    background:#d8d8d8;
    width:70px;
    height:70px;
    border-radius:100%;
    position: absolute;
    right: 16px;
    top:20px;
}
</style>
