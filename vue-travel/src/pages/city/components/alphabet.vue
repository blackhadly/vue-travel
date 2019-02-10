<template>
  <div>
    <ul class="list">
      <li class="item" v-for="item of letters" :key="item"
          :ref="item"
          @click="handleLetterClick"
          @touchstart.prevent="handleTouchStart"
          @touchmove="handleTouchMove"
          @touchend="handleTouchEnd"
      > {{item}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'alphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false
    }
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        const startY = this.$refs['A'][0].offsetTop
        const touchY = e.touches[0].clientY - startY
        const index = Math.floor((touchY - startY) / 20)
        if (index >= 0 && index < this.letters.length) {
          this.$emit('change', this.letters[index])
        }
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style scoped>
  .list {
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: absolute;
    top: 158px;
    right: 0;
    bottom: 0;
    width: 40px;
  }
  .item {
    line-height: 40px;
    text-align: center;
    color: #00bcd4;
  }
</style>
