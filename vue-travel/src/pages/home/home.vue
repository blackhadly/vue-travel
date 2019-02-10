<template>
    <div>
        <Header></Header>
        <swipper :list="swiperList"></swipper>
        <icons :list="iconList"></icons>
        <recommend :list="recommend"></recommend>
        <week :list="week"></week>
    </div>
</template>

<script>
import Header from './components/Header'
import swipper from './components/swipper'
import icons from './components/icons'
import recommend from './components/recommend'
import week from './components/week'

import axios from 'axios'

export default {
  name: 'Home',
  components: {
    Header,
    swipper,
    icons,
    recommend,
    week
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      recommend: [],
      week: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.$store.state.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommend = data.recommendList
        this.week = data.weekendList
      }
    }
  },
  mounted () {
    this.lastCity = this.$store.state.city
    this.getHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.$store.state.city) {
      this.lastCity = this.$store.state.city
      this.getHomeInfo()
    }
  }
}
</script>

<style>

</style>
