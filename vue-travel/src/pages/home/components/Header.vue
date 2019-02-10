<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont icon-fanhui">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont icon-sousuo">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to="/city">
            <div class="header-right">{{currentCity}}<span class="iconfont icon-jiantou">&#xe64a;</span></div>
        </router-link>
    </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
  name: 'Header',
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  }
}
</script>

<style scoped>
    .header{
        height:86px;
        line-height: 86px;
        display:flex;
        background: #00bcd4;
        color: #fff
    }
    .header-left{
        width:64px;
        float:left;
    }
    .icon-fanhui{
        text-align: center;
        font-size: 30px;
    }
    .header-input{
        flex:1;
        background: #fff;
        border-radius: 5px;
        margin-top: 12px;
        margin-left: 20px;
        padding-left: 20px;
        height: 64px;
        line-height: 64px;
        color: #ccc;
    }
    .header-right{
        width:124px;
        float:right;
        text-align: center;
        color:#fff;
    }
    .icon-jiantou{
        font-size: 20px;
    }
</style>
