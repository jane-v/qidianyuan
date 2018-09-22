<template>
  <section class="tabBar-wrap">
    <article class="tabBar-box">
      <ul class="tabBar-nav" v-if="navList.length > 0">
        <li v-for="(item, index) in navList"
            :class="['item', item.plus ? '':'']"
            @click="selectNavItem(index,item.pagePath)"
            :key="index">
          <span v-if="item.plus" class="fabu">+</span>
          <p v-if="item.selectedIconPath" class="item-images">
            <img :src="selectNavIndex === index ? item.selectedIconPath : item.iconPath" alt="iconPath">
          </p>
          <p v-if="item.selectedIconPath" :class="selectNavIndex === index ? 'item-text item-text-active' : 'item-text' ">
            {{item.text}}
          </p>
        </li>
        <!-- <li v-if="needButton" style="flex: 3">
          <div class="submit-box">
            <button :disabled="!handButton"
                    @click="bindNavigateTo('../order/main')"
                    :class="handButton ? 'submit-box-btn submit-box-btn-active' : 'submit-box-btn' ">
              {{ btnText }}
            </button>
          </div>
        </li> -->
      </ul>
    </article>
  </section>
</template>

<script>
//   import store from '../vuex/index'

export default {
  props: ['selectNavIndex'],
  data () {
    return {
      isshow: 'dfasdfsdf',
      navList: [
        {
          'pagePath': '/pages/home/main',
          'iconPath': '/static/images/nav_img_touxiang.png',
          'selectedIconPath': '/static/images/nav_img_touxiang.png',
          'text': '广场'
        },
        {
          'pagePath': '/pages/discovery/main',
          'iconPath': '/static/images/nav_img_touxiang.png',
          'selectedIconPath': '/static/images/nav_img_touxiang.png',
          'text': '发现'
        },
        {
          'pagePath': '/pages/home/main',
          'text': '发布',
          'plus': true
        },
        {
          'pagePath': '/pages/home/main',
          'iconPath': '/static/images/nav_img_touxiang.png',
          'selectedIconPath': '/static/images/nav_img_touxiang.png',
          'text': '优质'
        },
        {
          'pagePath': '/pages/mine/main',
          'iconPath': '/static/images/nav_img_touxiang.png',
          'selectedIconPath': '/static/images/nav_img_touxiang.png',
          'text': '我的'
        }
      ]
    }
  },
  created () {
  },
  methods: {
    /**
       * 点击导航栏
       * @param index
       */
    selectNavItem (index, pagePath) {
      console.log(this.selectNavIndex, index, pagePath)

      if (index === this.selectNavIndex) {
        return false
      }

      if (index === 0 && this.selectNavIndex === -1) {
        this.$emit('fetch-index')
      }
      if (index === 2) {
        this.bindNavigateTo(pagePath)
      } else {
        this.bindViewTap(pagePath)
      }
    },

    /**
       * 路由跳转
       */
    bindNavigateTo (url) {
      wx.navigateTo({
        url
      })
    },

    /**
       * tabBar路由跳转
       */
    bindViewTap (url) {
      // 回到顶部
      if (url === '../index/main') {
        //   store.commit('setGroupsID', '')
      }
      wx.switchTab({
        url
      })
    }
  }
}
</script>

<style lang="less" scoped>
  .tabBar-box {
    position: fixed;
    bottom: 0;
    width: 100%;
    height: 36px;
    padding: 5px 0;
    border-top: 1px solid #eee;
    background-color: #f8f8f8;
  }

  .tabBar-nav {
    width: 100%;
    display: flex;

    .fabu{
      height: 44px;
      width: 44px;
      border-radius: 40px;
      font-size: 44px;
      background: rgba(148, 132, 220, 1);
      color :#fff;
      margin-top:-15px;
      line-height: 35px;
      display:block;
      margin-left:15.5px;
      font-weight: 100;
    }

    .item {
      flex: 1;
      text-align: center;
    }
    .item-text {
      color: #666;
      font-size: 10px;
      transition: .24s linear;
    }
    .item-text-active {
      color: rgba(148, 132, 220, 1);
    }

    .item-images {
      width: 25px;
      height: 25px;
      margin: 0 auto;
      text-align: center;
      transition: .24s linear;

      & img {
        display: inline;
        width: 20px;
        height: 20px;
      }
    }
  }

  .submit-box-btn {
    position: relative;
    z-index: 999;
    width: 85%;
    height: 90px;
    line-height: 90px;
    border-radius: 10px;
    color: #404040;
    font-size: 36px;
    border: none;
    background-color: #eee;
    text-align: center;
    border: 1px solid #eee;
  }

  .submit-box-btn-active {
    color: #fff;
    border: none;
    border: 1px solid #ff6c00;
    background-color: #ff6c00;
  }

  button {
    border: none;
    outline: none;
  }
</style>