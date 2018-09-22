<template>
  <picker
      mode="multiSelector"
      @change="onChange"
      @columnchange="oncolumnchange"
      :value="multiIndex"
      :range="multiArray"
      v-model="multiArray"
    >
      <slot />
    </picker>
</template>

<script>
export default {
  data () {
    return {
      multiArray: [['系统推荐', '筛选身份', '行业选择'], ['最新', '热门'], []],
      multiIndex: [0, 0, 0]
    }
  },
  props: ['region'],
  methods: {
    onChange (e) {
      const value = e.target.value

      this.$emit('change', value)
      this.$emit('input', value)
    },
    oncolumnchange (e) {
      console.log(e)
      console.log('修改的列为', e.target.column, '，值为', e.target.value)
      //   this.multiArray = [['无脊柱动物', '脊柱动物'], ['扁性动物', '线形动物'], []]
      //   let multiArray = this.multiArray
      let multiIndex = []
      let multiArray = []

      multiArray[0] = this.multiArray[0]

      switch (e.target.column) {
        case 0:
          console.log('1111111')
          multiIndex[0] = e.target.value
          switch (multiIndex[0]) {
            case 0:
              multiArray[1] = ['最新', '热门']
              multiArray[2] = []
              break
            case 1:
              multiArray[1] = ['甲方', '乙方']
              multiArray[2] = []
              break
            case 2:
              multiArray[1] = ['软件开发', '电子购物', '金融']
              multiArray[2] = ['鲫鱼', '带鱼']
              break
          }
          multiIndex[1] = 0
          multiIndex[2] = 0
          break
        // case 1:
        //   console.log('2222222')
        //   multiIndex[0] = this.multiIndex[0]
        //   multiIndex[1] = e.target.value
        //   switch (multiIndex[0]) {
        //     case 0:
        //       multiArray[2] = []
        //       break
        //     case 1:
        //       multiArray[2] = []
        //       break
        //     case 2:
        //       switch (multiIndex[1]) {
        //         case 0:
        //           multiArray[2] = ['鲫鱼', '带鱼']
        //           break
        //         case 1:
        //           multiArray[2] = ['青蛙', '娃娃鱼']
        //           break
        //         case 2:
        //           multiArray[2] = ['蜥蜴', '龟', '壁虎']
        //           break
        //       }
        //       break
        //   }
        //   multiIndex[2] = 0
        //   break
        // case 2:
        //   multiIndex[0] = this.multiIndex[0]
        //   multiIndex[1] = this.multiIndex[1]
        //   multiIndex[2] = e.target.value
        //   break
      }
      //   console.log(multiArray)
      console.log(multiIndex)
      this.multiArray = multiArray
      this.multiIndex = multiIndex
      this.$emit('change', multiIndex)
      this.$emit('input', multiIndex)
    //   console.log(this.multiArray)
    //   this.setData({multiArray: multiArray})
    }
  }
}
</script>

<style>
.card {
  padding: 10px;
}
</style>
