<template>
  <div>
    <div class="banner"  @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" />
      <div class="banner-info">
        <div class="banner-tittle">
          {{sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe632;</span>
          {{bannerImgs.length}}
        </div>
      </div>
    </div>
    <FadeAnimation>
      <Gallery :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></Gallery>
    </FadeAnimation>
  </div>
</template>

<script>
import Gallery from '@/common/gallery'
import FadeAnimation from '@/common/fade'
export default {
  name: 'banner',
  components: {
    Gallery,
    FadeAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style scoped>
  .banner {
    position: relative;
    overflow: hidden;
    height: 0;
    padding-bottom: 55%;
  }

  .banner-img {
    width: 100%;
  }

  .banner-info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: 60px;
    color: #fff;
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
  }

  .banner-tittle {
    flex: 1;
    font-size: 32px;
    padding: 0 20px;
  }

  .banner-number {
    height: 32px;
    line-height: 32px;
    margin-top: 14px;
    padding: 0 40px;
    border-radius: 20px;
    background: rgba(0, 0, 0, .8);
    font-size: 24px;
  }

  .banner-icon {
    font-size: 24px;
  }
</style>
