<template>
    <div>
        <Header></Header>
        <swipper></swipper>
        <icons></icons>
    </div>
</template>

<script>
import Header from './components/Header'
import swipper from './components/swipper'
import icons from './components/icons'

export default {
  name: 'Home',
  components: {
    Header,
    swipper,
    icons
  }
}
</script>

<style>

</style>
