<template>
  <section class="demand_card">
      <img :src="imglist[type]" alt="iconPath">
  </section>
</template>

<script>
export default {
  data () {
    return {
      imglist: {
        renZheng: '/static/images/img_renzheng.png',
        vip0: '/static/images/img_vip0.png',
        vip1: '/static/images/img_vip1.png',
        vip2: '/static/images/img_vip2.png',
        vip3: '/static/images/img_vip3.png'
      }
    }
  },
  props: ['type']
}
</script>

<style lang="less" scoped>
.demand_card {
  display:inline-block;
  margin-left:10px;
  img{
      width:42px;
      height: 16px;
  }
}
</style>
