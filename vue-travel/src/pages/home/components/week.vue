<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of recommendList"
        :key="item.id"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'recommend',
  data () {
    return {
      recommendList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a3/9c9d78e925e8bc.jpg_r_640x214_74656d68.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a3/9c9d78e925e8bc.jpg_r_640x214_74656d68.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a3/9c9d78e925e8bc.jpg_r_640x214_74656d68.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a3/9c9d78e925e8bc.jpg_r_640x214_74656d68.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '005',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a3/9c9d78e925e8bc.jpg_r_640x214_74656d68.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '006',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a3/9c9d78e925e8bc.jpg_r_640x214_74656d68.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        }
      ]
    }
  }
}
</script>

<style scoped>
  .title {
    margin-top: 20px;
    line-height: 80px;
    background: #eee;
    text-indent: 20px;
  }

  .item-img-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 37.09%;
  }

  .item-img {
    width: 100%
  }

  .item-info {
    padding: 10px;
  }

  .item-title {
    line-height: 54px;
    font-size: 32px;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis
  }

  .item-desc {
    line-height: 40px;
    color: #ccc;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis
  }
</style>
