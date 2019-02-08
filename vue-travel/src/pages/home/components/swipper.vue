<template>
    <div class="wrapper">
        <swiper :options="swiperOption" ref="mySwiper" v-if="list.length">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swipper-img"
                     :src="item.imgUrl"
                     alt="">
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'swipper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        loop: true
      }
    }
  }
}
</script>

<style scoped>
    .swipper-img{
         width: 100%;
    }
    .wrapper{
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom:26.7%;
    }
    .wrapper >>> .swiper-pagination-bullet-active {
    background: #fff
    }
</style>
