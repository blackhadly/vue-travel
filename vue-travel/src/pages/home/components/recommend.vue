<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <li
                class="item border-bottom"
                v-for="item of recommendList"
                :key="item.id"
            >
                <img class="item-img" :src="item.imgUrl" />
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
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
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          desc: '世界五大宫之首，穿越与您近在咫尺'
        },
        {
          id: '006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
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
    .item {
        overflow: hidden;
        display: flex;
        height: 190px
    }
    .item-img {
        width: 170px;
        height: 170px;
        padding: 10px;
    }
    .item-info {
        flex: 1;
        padding: 10px;
        min-width: 0
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
        color: #ccc ;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis
    }

    .item-button {
        line-height: 44px;
        margin-top: 16px;
        background: #ff9300;
        padding: 10px;
        border-radius: 6px;
        color: #fff;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis
    }
</style>
