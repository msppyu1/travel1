<template>
<div>

     <div class="banner" @click="handleGallaryClick">
  <img class="banner-img" :src="bannerImg" alt="">
  <div class="banner-info">
      <div class="banner-tittle">{{this.sightName}}</div>
      <div class="banner-number"><span class="iconfont">&#xe6dd;</span> {{this.bannerImgs.length}}</div>
  </div>
  </div>
  <Fade>
  <common-gallery :imgs="bannerImgs" v-show="showGallery"></common-gallery>
   </Fade>
</div>

</template>

<script>
import CommonGallery from 'common/gallary/Gallary'
import Fade from 'common/fade/Fade'
export default {
  name: 'Banner',
  props: [
    'sightName',
    'bannerImg',
    'bannerImgs'
  ],
   
  components:{
      CommonGallery,
      Fade
  },
  data () {
    return {
        showGallery:false,
    
    }
  },
  methods:{
      handleGallaryClick () {
          this.showGallery=true
      }
  }
}
</script>

<style lang="stylus" scoped>
 .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-tittle
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
