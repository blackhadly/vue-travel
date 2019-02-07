<template>
    <div class="wrapper">
        <swiper :options="swiperOption" ref="mySwiper">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/74552617e27d66916156dbb6ee38379e.jpg_750x200_0ad3c4be.jpg'
        },
        {
          id: '0002',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/99d97f5421741c2a2028dced52b66391.jpg_750x200_9e38628d.jpg'
        },
        {
          id: '0003',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/74552617e27d66916156dbb6ee38379e.jpg_750x200_0ad3c4be.jpg'
        },
        {
          id: '0004',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/99d97f5421741c2a2028dced52b66391.jpg_750x200_9e38628d.jpg'
        }
      ]
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
