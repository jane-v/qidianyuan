<template>
  <li class="demand">
    <section class="demand_content">
        <span class="name">用户昵称</span>·<span class="title">高级项目</span>
        <demand-card type="vip1"></demand-card><demand-card type="renZheng"></demand-card>
        <section class="attention">
          <img src="/static/images/img_attention.png">
          118w
        </section>
        <p>花神本名陈佳锋，广州人士，18岁外出打工挣到第一桶金。随后回到广州本市投资建房，广施善财，结交权贵。短短3年时间已成为广州十大杰出青年代表。</p>
        <demand-tip tip="预算"></demand-tip>
        <demand-tip tip="期望周期"></demand-tip>
        <demand-tip tip="计算方式"></demand-tip>
        <section class="order_date">订单时间：2018/09/09 — 2018/09/10</section>
        <a href="/pages/home/main" class="detail">查看详情></a>
    </section>
  </li>
</template>

<script>
import demandCard from '@/components/demandCard'
import demandTip from '@/components/demandTip'
export default {
  data () {
    return {
      lll: '123345'
    }
  },
  props: ['text'],
  components: {
    demandCard,
    demandTip
  }
}
</script>

<style lang="less" scoped>
.demand{
    background: #f5f5f5;
    padding-bottom: 6px;
    .demand_content{
      background: #fff;
      padding: 20px 16px;
      position:relative;
    }
    .name,.title{
      font-size:16px;
      color:#000000;
    }
    p{
      font-size: 12px;
      color:#000000;
    }
    .order_date{
      font-size:12px;
      color:#666666;
      line-height:12px;
      text-align:left;
      margin-top:12px;
    }
    .detail{
      font-size:12px;
      color:#7a87ff;
      line-height:12px;
      position: absolute;
      right: 16px;
      bottom:20px;
    }
    .attention{
      float:right;
      font-size:12px;
      color:#666666;
      line-height:30px;
      img{
        width: 17px;
        height: 12px;
      }
    }
}

.imgcontainer {
  height: 70px;
  width: 70px;
  border: rgba(204, 204, 204, 1) solid 1px;
  border-radius: 16px;
}
</style>
