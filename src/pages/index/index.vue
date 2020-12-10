<template>
    <div>
        <div class="banner">
            <img class="userinfo-avatar" mode="widthFix" :src="imgUrl" />
        </div>
        <div class="box">
            <div class="title">title1</div>
            <van-grid :border="true" icon-size="32px">
                <van-grid-item icon="photo-o" text="文字" @click="clickHandle"/>
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
            </van-grid>
        </div>
        <div class="box">
            <div class="title">title2</div>
            <van-grid :border="true">
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
            </van-grid>
        </div>
        <div class="box">
            <div class="title">title3</div>
            <van-grid :border="true">
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
                <van-grid-item icon="photo-o" text="文字" />
            </van-grid>
        </div>
  </div>
</template>

<script>

export default {
    onLoad(){
        wx.setNavigationBarTitle({
          title:'我是标题',
        })
        wx.setNavigationBarColor({
          frontColor:'#ffffff',//前景颜色值，包括按钮、标题、状态栏的颜色，仅支持 #ffffff 和 #000000 (微信小程序官方规定)
          backgroundColor:'#000000'//背景颜色值，有效值为十六进制颜色
        })
    },
  data () {
    return {
      imgUrl:'/static/images/banner1.jpg'
    }
  },


  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    clickHandle (ev) {
        const url = '../logs/main'
        console.log('clickHandle:', ev)
        mpvue.navigateTo({ url })
      // throw {message: 'custom test'}
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped>

.userinfo-avatar {
  width: 100%;
  height: auto;
}

.title{
    padding: 10px;
}
</style>
