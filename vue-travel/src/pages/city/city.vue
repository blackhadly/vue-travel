<template>
  <div >
    <Header ></Header>
    <search :cities="cities"></search>
    <list :cities="cities" :hot="hotCities" :letter="letter"></list>
    <alpha :cities="cities" @change="handleLetterChange"></alpha>
  </div>
</template>

<script>
import Header from './components/Header'
import search from './components/search'
import list from './components/list'
import alpha from './components/alphabet'

import axios from 'axios'

export default {
  name: 'city',
  components: {
    Header,
    search,
    list,
    alpha
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.getCityInfoSucc)
    },
    getCityInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
        this.iconList = data.iconList
        this.recommend = data.recommendList
        this.week = data.weekendList
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style scoped>

</style>
