<template>
  <div>
    <p class="card">
      {{text}}{{lll}}
    </p>
  </div>
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

<style>
.card {
  padding: 10px;
}
</style>
