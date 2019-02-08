<template>
    <div>
        <Header></Header>
        <swipper></swipper>
        <icons></icons>
        <recommend></recommend>
        <week></week>
    </div>
</template>

<script>
import Header from './components/Header'
import swipper from './components/swipper'
import icons from './components/icons'
import recommend from './components/recommend'
import week from './components/week'

export default {
  name: 'Home',
  components: {
    Header,
    swipper,
    icons,
    recommend,
    week
  }
}
</script>

<style>

</style>
