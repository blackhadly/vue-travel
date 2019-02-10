<template>
  <div>
    <Banner :sightName="sightName"
            :bannerImg="bannerImg"
            :bannerImgs="gallaryImgs">
    </Banner>
    <Header></Header>
    <div class="content">
      <list :list="list"></list>
    </div>
  </div>
</template>

<script>
import Banner from './compents/banner'
import Header from './compents/header'
import list from './compents/list'

import axios from 'axios'

export default {
  name: 'detail',
  components: {
    Banner,
    Header,
    list
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style scoped>
  .content {
    height: 5000px;
  }
</style>
