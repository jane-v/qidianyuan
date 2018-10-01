<template>
  <div class="webview">
      <web-view :src='url'></web-view>
  </div>
</template>

<script>
// onLoad: function (options) {
//  this.setData({
//    url: decodeURIComponent(options.url),
//  });
// },

// // 接收 h5 页面传递过来的参数
// handlePostMessage: function (e) {
//   const data = e.detail;
//   console.log(data);
// }

export default {
  data: function () {
    return {
      url: ''
    }
  },
  onLoad: function (options) {
    console.log(options)
    this.url = decodeURIComponent(options.url)
  }
}
</script>

<style lang="less" scoped>

</style>