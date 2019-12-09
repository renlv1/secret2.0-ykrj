<template>
  <div class="wrapper">
    <div class="wrapper-pc" ref="height4">
      <div class="banner banner-m-t">
        <img :src="require(`@img/gif2/proCommunity/banner_${$lang}.svg`)" alt=""  class="img-c-m">
        <div class="gif">
          <img src="@img/gif2/proCommunity/proCommunity.gif" alt="" class="gif-img">
        </div>
      </div>
    </div>
    <div class="wrapper-pc" ref="height1">
      <div class="section s1">
        <div class="wrap">
          <div class="content">
            <span class="num"><img src="@com/01.svg" alt=""></span>
            <div class="title">{{$t('proCommunity.text3')}}</div>
            <p class="description">{{$t('proCommunity.text4')}}</p>
            <p class="description">{{$t('proCommunity.text5')}}</p>
            <p class="description">{{$t('proCommunity.text6')}}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="wrapper-pc" ref="height2">
      <div class="section s2 bgf">
        <div class="wrap">
          <div class="flex">
            <div class="img img-banner">
              <img src="@img/community/banner2.gif" alt="">
            </div>
            <div class="text">
              <span class="num"><img src="@com/02.svg" alt=""></span>
              <div class="title">{{$t('proCommunity.text7')}}</div>
              <p class="description">{{$t('proCommunity.text8')}}</p>
              <p class="description">{{$t('proCommunity.text8_1')}}</p>
              <p class="description">{{$t('proCommunity.text9')}}</p>
              <p class="description">{{$t('proCommunity.text9_1')}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="wrapper-pc" ref="height3">
      <div class="section s3">
        <div class="wrap">
          <span class="num"><img src="@com/03.svg" alt=""></span>
          <p class="title">{{$t('proCommunity.text14')}}</p>
          <p class="description">{{$t('proCommunity.text15')}}</p>
          <div class="group">
            <div class="list" v-for="(list, i) in allList" :key="i" :class="{'first-list': i === 0}">
              <div class="item" v-for="(item, index) in allList[i]" :key="index">
                <div class="img">
                  <img :src="item.imgUrl" alt="">
                </div>
                <h3>{{item.title}}</h3>
                <p>{{item.description}}</p>
              </div>
            </div>
          </div>
          <div class="down">
            <div class="text">
              <p>{{$t('proCommunity.text17')}}</p>
              <p>{{$t('proCommunity.text17_1')}}</p>
              <p v-if="$lang === 'cn'">{{$t('proCommunity.text17_2')}}</p>
            </div>
            <div class="btn" @click="download">{{$t('proCommunity.text18')}}</div>
          </div>
        </div>
      </div>
    </div>

    <div class="wrapper-mobile" ref="mheihgt4">
      <div class="banner">
        <img :src="require(`@img/community/mobile_banner_${$lang}.svg`)" alt="">
      </div>
    </div>
    <div class="wrapper-mobile" ref="mheihgt3">
      <div class="banner-wrapper-mobile">
        <div class="wrapper-mobile-top">
          <div class="num">
            <img src="../assets/img/borderNumber/01.svg" alt="">
          </div>
          <!--          <div class="one-banner"></div>-->
        </div>
        <div class="wrapper-mobile-content">
          <p class="title">{{$t('proCommunity.text3')}}</p>
          <p class="description">{{$t('proCommunity.text4')}}</p>
          <p class="description">{{$t('proCommunity.text5')}}</p>
          <p class="description">{{$t('proCommunity.text6')}}</p>
        </div>
        <div class="banner-bg"></div>
      </div>
    </div>
    <div class="wrapper-mobile" ref="mheihgt2">
      <div class="content-one-mobile">
        <div class="top">
          <div class="content-left">
            <img src="../assets/img/community/banner2.gif" />
          </div>
          <div class="content-right">
            <span class="num">
              <img src="../assets/img/borderNumber/02.svg" alt="">
            </span>
            <p class="title">{{$t('proCommunity.text7')}}</p>
          </div>
        </div>
        <p class="description">{{$t('proCommunity.text8')}}</p>
        <p class="description">{{$t('proCommunity.text8_1')}}</p>
        <p class="description">{{$t('proCommunity.text9')}}</p>
        <p class="description">{{$t('proCommunity.text9_1')}}</p>
      </div>
    </div>
    <div class="wrapper-mobile" ref="mheihgt1">
      <div class="content-two-mobile">
        <div class="num">
          <img src="../assets/img/borderNumber/03.svg" alt="">
        </div>
        <div class="title">{{$t('proCommunity.text14')}}</div>
        <div class="description">{{$t('proCommunity.text15')}}</div>
        <div class="list-wrapper">
          <ul class="left-list">
            <li class="item">
              <div class="item-top">
                <img :src="leftList[0].imgUrl" />
                <p class="title">{{leftList[0].title}}</p>
              </div>
              <p class="description">{{leftList[0].description}}</p>
            </li>
            <li class="item">
              <div class="item-top">
                <img :src="leftList[1].imgUrl" />
                <p class="title">{{leftList[1].title}}</p>
              </div>
              <p class="description">{{leftList[1].description}}</p>
            </li>
            <li class="item">
              <div class="item-top">
                <img :src="leftList[2].imgUrl" />
                <p class="title">{{leftList[2].title}}</p>
              </div>
              <p class="description">{{leftList[2].description}}</p>
            </li>
            <li class="item hasBorder">
              <div class="item-top">
                <img :src="leftList[3].imgUrl" />
                <p class="title">{{leftList[3].title}}</p>
              </div>
              <p class="description">{{leftList[3].description}}</p>
            </li>
          </ul>
          <ul class="right-list">
            <li v-for="item in rightList" :key="item.index">
              <div class="item-top">
                <img :src="item.imgUrl" />
                <p class="title">{{item.title}}</p>
              </div>
              <p class="description">{{item.description}}</p>
            </li>
          </ul>
        </div>
        <div class="other-li">
          <div class="subTitle">
            {{$t('proCommunity.text17')}}
          </div>
          <div class="subTitle">{{$t('proCommunity.text17_1')}}{{$t('proCommunity.text17_2')}}！</div>
          <div class="btn" @click="openStart">{{$t('proCommunity.text18')}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
  .banner-m-t{
    position: relative;
    .gif{
      position: absolute;
      right: 500px;
      top: 50%;
      transform: translateY(-50%);
      margin-top: -100px;
      @media screen and (max-width: 1950px){
        right: 300px;
      }
      @media screen and (max-width: 1800px){
        right: 100px;
      }
      @media screen and (max-width: 1600px){
        width: 600px;
        right: 300px;
      }
      @media screen and (max-width: 1400px){
        right: 100px;
      }
    }
  }
  .wrap {
    width: 1200px;
    margin: 0 auto;
    color: #636e72;
    @media (max-width: 1400px) {
      width: 100%;
      padding: 0 40px;
      margin: 0 auto;
    }
  }

  img {
    max-width: 100%;
    vertical-align: top
  }

  .flex {
    display: flex;
    align-content: center;
    justify-content: space-between;
  }

  .title {
    font-size: 30px;
    color: #2d3436;
    font-weight: bold;
    line-height: 1;
    padding: 40px 0 30px;
  }

  p + p {
    padding-top: 2px;
    font-size: 16px;
  }

  .banner {
    box-shadow: 0 2px 10px rgba(0, 0, 0, .05);
    position: relative;
    img {
      width: 100%;
    }
  }

  .section {
    background: #fafafa;
    &.bgf {
      background: #fff;
      .img-banner{
        width: 446px;
      }
    }
  }

  .s1 {
    padding-bottom: 135px;
    padding-top: 0;
    .wrap {
      position: relative;
      margin-top: -80px;
      &:before {
        content: '';
        position: absolute;
        width: 630px;
        height: 135px;
        background: url("../assets/img/product/bg.png") no-repeat;
        background-position: right;
        right: -96px;
        bottom: -82px;
        @media (max-width: 1600px) {
          right: 0
        }
      }
    }
    .content {
      position: relative;
      background: #fff;
      box-shadow: 0 0 10px rgba(0, 0, 0, .15);
      padding: 60px;
      .description {
        font-size: 16px;
        line-height: 1.8;
      }
    }
    .play-btn {
      padding: 100px 0 10px;
    }
  }

  .s2 {
    padding: 84px 0;
    .text {
      padding-top: 30px;
      text-align: right;
      width: 650px;
      p {
        font-size: 16px;
        margin-right: -5px;
        line-height: 1.8;
      }
    }
  }

  .s3 {
    padding: 90px 0 130px;
    .group {
      display: flex;
      justify-content: center;
      padding-top: 180px;
      .list {
        width: 400px;
        border-left: 1px solid #c6c6c6;
        border-right: 1px solid #c6c6c6;
        &.first-list{
          border-bottom: 1px solid #c6c6c6;
          .item:last-child {
            border-bottom: none;
          }
        }
        &:nth-child(2) {
          margin-top: -90px;
          border-left: none;
          border-right: none;
          position: relative;
          &::before, &::after {
            content: '';
            position: absolute;
            background: #c6c6c6;
            width: 1px;
            height: 200px;
            top: 0;
          }
          &::before {
            left: -1px;
          }
          &::after {
            right: -1px;
          }
        }
      }
      .item {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 0 34px 20px;
        border-top: 1px solid #c6c6c6;
        font-size: 14px;
        line-height: 1.8;
        min-height: 270px;
        .en & {
          min-height: 320px;
        }
        &:last-child {
          border-bottom: 1px solid #c6c6c6;
        }
        .img {
          height: 110px;
          display: flex;
          align-items: center;
        }
        h3 {
          font-size: 20px;
          color: #2d3436;
          font-weight: bold;
          margin-bottom: 20px;
        }
      }
    }
    .down {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 400px;
      margin: -55px auto;
      position: relative;
      .text {
        .en & {
          padding-left: 55px;
        }
        font-size: 30px;
        font-weight: bold;
        color: #2d3436;
        p {
          font-size: 20px;
          margin-bottom: 10px;
        }
      }
      .btn {
        color: #2d3436;
        border: 1px solid;
        text-align: center;
        width: 250px;
        margin: 30px auto;
        line-height: 50px;
        font-size: 14px;
        cursor: pointer;
        transition: .3s;
        &:hover {
          background: #0080f4;
          color: #fff;
        }
      }
    }
  }
</style>
<style lang="stylus" rel="stylesheet/stylus" scoped>
  .banner-wrapper-mobile
    margin-top 50px
    position relative
    z-index 2
    width 100%
    background-color #fff
    padding-bottom 20px
    @media (max-width: 768px) {
      width 100%
      margin 50px auto
      overflow hidden
    }
    .wrapper-mobile-top
      display flex
      flex-direction row
      width 670px
      @media (max-width: 768px) {
        width 90%
      }
      .num
        z-index 999
        margin 18px 0 0 18px
        display block
      .one-banner
        margin-top 18px
        width 460px
        height 269px
        background url("../assets/img/product/02bg.svg") no-repeat
        background-size 460px 269px
        @media (max-width: 768px) {
          width 85%
          height 169px
          background-size 100% 169px
        }
        @media (max-width: 320px) {
          margin-top 0
        }
    .wrapper-mobile-content
      margin 0 20px
      .title
        font-size 16px
        color #2d3436
        font-weight bold
        margin 30px 0
        padding 0
      .description
        font-size 14px
        padding 0
        color #636e72
        line-height 2
      .play
        cursor pointer
        user-select none
        width 20px
        height 16px
        background url("../assets/img/product/play.svg") no-repeat
        background-size 20px 16px
    .banner-bg
      position absolute
      width 80%
      height 62px
      background url("../assets/img/product/bg.png") no-repeat
      background-size 80% 62px
      background-position right
      right -30px
      bottom -30px

  .content-one-mobile
    margin 90px 30px 0
    .top
      margin-bottom 30px
      display flex
      justify-content space-between
      align-items center
      .content-left
        width 50%
        img
          width 100%
      .content-right
        flex 1
        display flex
        flex-direction column
        align-items flex-end
        .num
          display block
        .title
          text-align right
          margin 20px 0
          font-size 16px
          color #2d3436
          font-weight bold
          @media screen and (max-width: 1200px)
            padding: 0
            font-size: 14px
    .description
      font-size 14px
      color #636e72
      line-height 1.8

  .content-two-mobile
    background-color #f7f7f7
    margin 60px 30px 100px
    position relative
    @media screen and (max-width: 1200px)
      margin: 30px 0 0
      padding 30px 20px 30px
    .num
      display block
    .title
      margin 20px 0
      font-size 16px
      color #2d3436
      font-weight bold
      padding 0
    .description
      font-size 14px
      color #636e72
      line-height 2
    .btn
      position absolute
      margin-top 40px
      cursor pointer
      user-select none
      font-size 16px
      color #636e72
      text-align center
      line-height 40px
      height 40px
      width 125px
      border 1px solid #2d3436
    .list-wrapper
      margin-top 40px
      display flex
      flex-direction row
      .left-list
        width 50%
        margin-top 90px
        .item
          border 1px solid #c6c6c6
          border-right none
          border-bottom none
          min-height 220px
          padding-bottom 5px
          .item-top
            margin 10px 10px 5px
            display flex
            flex-direction row
            img
              margin-right 15px
              @media (max-width: 768px) {
                width 30%
              }
              @media (max-width: 374px) {
                margin-right 5px
              }
          .description
            margin 0 8px
            font-size 12px
            line-height 1.6
        .hasBorder
          border-bottom 1px solid #c6c6c6
      .right-list
        width 50%
        li
          min-height 220px
          border 1px solid #c6c6c6
          border-bottom none
          padding-bottom 5px
          .item-top
            margin 10px 10px 5px
            display flex
            flex-direction row
            img
              margin-right 15px
              @media (max-width: 768px) {
                width 30%
              }
              @media (max-width: 374px) {
                margin-right 5px
              }
          &:last-child
            border-bottom 1px solid #c6c6c6
          .description
            margin 0 8px
            font-size 12px
            line-height 1.6
    .other-li
      width 50%
      position absolute
      bottom 10px
      left 0
      margin: 30px 0 80px
      padding 30px 28px 0
      @media (max-width: 414px){
        margin: 40px 0 80px
        bottom 0
      }
      .subTitle
        font-size 14px
        width 100%
        line-height 1.4
        font-weight bold
        color #2d3436
        @media (min-width: 414px) and (max-width: 580px) {
          width 100%
        }
        @media (min-width: 580px) and (max-width: 725px) {
          width 80%
        }
      .btn
        border 1px solid #0080f4
        font-size 14 pxd
        margin-top 20px
</style>

<script>
export default {
  name: "proCommunity",
  data() {
    return {
      leftList: this.$t('proCommunity.leftList'),
      rightList: this.$t('proCommunity.rightList'),
      isEN: false,
    }
  },
  computed: {
    allList() {
      let arr = [
        [
          this.leftList[0],
          this.rightList[1],
          this.leftList[3],
        ],
        [
          this.rightList[0],
          this.leftList[2],
          this.rightList[3],
        ],
        [
          this.leftList[1],
          this.rightList[2],
          this.rightList[4],
        ]
      ]

      return arr
    }
  },
  created() {
    if (window.localStorage.getItem('secretLang') === 'EN') {
      this.isEN = true
    } else {
      this.isEN = false
    }

    if (this.$route.query.a) {
      setTimeout(() => {
        if (window.innerWidth > 1200) {
          document.body.scrollTop = document.documentElement.scrollTop = this.$refs.height1.clientHeight + this.$refs.height2.clientHeight + this.$refs.height4.clientHeight
        } else {
          document.body.scrollTop = document.documentElement.scrollTop = this.$refs.mheihgt2.clientHeight + this.$refs.mheihgt3.clientHeight + this.$refs.mheihgt4.clientHeight + 160
        }
      }, 500)
    }
  },
  methods: {
    openStart() {
      this.$router.push('/tradingCenter')
    },
    download() {
      window.open('https://isecret.im/', '_blank');
    }
  }
}
</script>
