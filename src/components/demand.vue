<template>
  <li class="demand">
    <section class="imgcontainer">

    </section>
    <section>
        <span>用户昵称</span>
    
    </section>
  </li>
</template>

<script>
export default {
  data () {
    return {
      lll: '123345'
    }
  },
  props: ['text']
}
</script>

<style scoped>
.demand{
    border:rgba(204, 204, 204, 1) solid 1px;
    border-radius: 6px;
    padding: 9px 6px;
    margin-top: 14px;
}
.imgcontainer {
  height: 70px;
  width: 70px;
  border: rgba(204, 204, 204, 1) solid 1px;
  border-radius: 16px;
}
</style>
