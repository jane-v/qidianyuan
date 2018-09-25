<template>
  <section class="demand_tip">
      {{tip}}
  </section>
</template>

<script>
export default {
  props: ['tip']
}
</script>

<style scoped>
.demand_tip {
  width: 56px;
  height: 20px;
  display:inline-block;
  margin-right:4px;
  background:#7a87ff;
  font-size: 12px;
  color:#fff;
  border-radius:2px;
  text-align: center;
}
</style>
