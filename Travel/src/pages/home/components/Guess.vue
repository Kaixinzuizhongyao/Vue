<template>
  <div class="guess">
    <div class="title">
      <img class="title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="猜你喜欢">
      <span class="title-txt">猜你喜欢</span>
    </div>
    <ul class="list">
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <a class="item-link" :href="item.linkUrl">
          <div class="item-img">
            <img class="item-like-img" :src="item.imgUrl">
          </div>
          <div class="item-tag" v-if="item.tagName === '随买随用'" style="background: #ffaa1e">{{item.tagName}}</div>
          <div class="item-tag" v-else-if="item.tagName === '可订明日'" style="background: #08CFE9">{{item.tagName}}</div>
          <div class="item-info">
            <div class="info-title">{{item.title}}</div>
            <div class="info-comment">
              <span class="starlevel">
                <span class="starlevel-gain iconfont" :style="{width: item.grade*10 + '%'}">&#xe81b;&#xe81b;&#xe81b;&#xe81b;&#xe81b;</span>
                <span class="iconfont starlevel-total">&#xe81b;&#xe81b;&#xe81b;&#xe81b;&#xe81b;</span>
              </span>
              <span class="comment-num">{{item.commentNum}}条评论</span>
            </div>
            <div class="info-price">
              <span class="price">
                ￥
                <em class="price-num">{{item.price}}</em>
              </span>起
              <span class="address">{{item.address}}</span>
            </div>
            <div class="info-feature" v-if="item.feature">
              {{item.feature}}
            </div>
          </div>
        </a>
      </li>
    </ul>
    <a href="http://touch.piao.qunar.com/touch/list_南京_景点门票.html" class="more border-top">查看所有产品</a>
  </div>
</template>

<script>
export default {
  name: 'HomeGuess',
  props: {
    list: Array
  },
  data () {
    return {
      tagStyle: {
        // background: '#ffaa1e'
      },
      starStyle: {
        width: ''
      }
    }
  },
  methods: {
    changeTagStyle () {

    },
    changeStarStyle () {

    }
  },
  mounted () {
    this.changeTagStyle()
    this.changeStarStyle()
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.guess
  margin-top 0.2rem
  background #fff
.title
  padding 0.24rem 0 0.26rem
  .title-img
    display inline-block
    overflow hidden
    width 0.3rem
    height 0.3rem
    margin-left 0.2rem
    vertical-align top
  .title-txt
    display inline-block
    margin-left 0.08rem
    height 0.44rem
    width 6rem
    color #212121
    font-size 0.32rem
    line-height 0.44rem
    ellipsis()
.list
  margin-left 0.24rem
  .item
    position relative
    overflow hidden
    padding 0.2rem 0
    .item-link
      width 100%
      height 100%
      .item-img
        float left
        overflow hidden
        width 2rem
        height 2rem
        background #f0f5f8
        .item-like-img
          width 100%
          height 100%
      .item-tag
        position absolute
        top 0.2rem
        left 0
        width 1.02rem
        height 0.38rem
        background-size 100%
        // background-color #ffaa1e
        border-bottom-right-radius 0.2rem
        color #fff
        font-size 0.2rem
        line-height 0.38rem
        text-indent 0.04rem
      .item-info
        overflow hidden
        padding-left 0.22rem
        .info-title
          margin-top 0.26rem
          height 0.44rem
          color #212121
          font-size 0.32rem
          line-height 0.44rem
        .info-comment
          margin-top 0.14rem
          height 0.34rem
          .starlevel
            display inline-block
            position relative
            width 1.2rem
            margin-right 0.3rem
            height 0.28rem
            line-height 0.28rem
            .starlevel-gain
              z-index 2
              position absolute
              overflow hidden
              // width 90%
              top 0.04rem
              left 0
              height 0.28rem
              color #ffb436
              font-size 0.24rem
            .starlevel-total
              z-index 1
              color #e0e0e0
              overflow hidden
              position absolute
              top 0.04rem
              left 0
              height 0.28rem
              font-size 0.24rem
          .comment-num
            color #616161
            font-size 0.24rem
            line-height 0.34rem
            vertical-align text-bottom
        .info-price
          position relative
          margin-top 0.22rem
          color #616161
          font-size 0.24rem
          line-height 0.4rem
          .price
            color #ff8300
            .price-num
              font-size 0.4rem
              margin-left -0.1rem
          .address
            position absolute
            right 0.24rem
            bottom 0
            width 1.2rem
            text-align right
            ellipsis()
        .info-feature
          display inline-block
          margin-top 0.48rem
          margin-right 0.24rem
          background #fff9f9
          padding 0.04rem 0.1rem
          color #f55
          font-size 0.24rem
          line-height 0.34rem
.more
  display block
  padding 0.2rem 0
  color #00afc7
  font-size 0.28rem
  line-height 0.4rem
  text-align center
</style>
