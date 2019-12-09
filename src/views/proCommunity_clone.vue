<template>
  <div class="wrapper">
<!--    不要-->
    <div class="wrapper-pc">
      <div class="wrapper-top">
        <div class="top-content" :class="[$lang !== 'cn' ? 'enPcHasLetter': 'cnPcHasLetter']">
          <span class="subTitle">OUR MISSION</span>
          <span class="title title-middle">{{$t('proCommunity.text1')}}</span>
          <span class="title">{{$t('proCommunity.text1a')}}</span>
        </div>
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="wrapper-top-mobile">
        <div class="top-content" :class="{'isMobileHasLetter': !isEN}">
          <span class="subTitle">OUR MISSION</span>
          <span class="title title-middle">{{$t('proCommunity.text1')}}</span>
          <span class="title">{{$t('proCommunity.text1a')}}</span>
        </div>
      </div>
    </div>
    <div class="wrapper-pc">
      <div class="banner-wrapper">
        <div class="banner">
          <span class="num"></span>
          <p class="title">{{$t('proCommunity.text3')}}</p>
          <p class="description">{{$t('proCommunity.text4')}}</p>
          <p class="description">{{$t('proCommunity.text5')}}</p>
          <p class="description">{{$t('proCommunity.text6')}}</p>
        </div>
        <div class="banner-bg"></div>
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="banner-wrapper-mobile">
        <div class="wrapper-mobile-top">
          <div class="num"></div>
          <div class="one-banner"></div>
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
    <div class="wrapper-mobile">
      <div class="content-one-mobile">
        <div class="top">
          <div class="content-left">
            <img src="../assets/img/community/1.svg" />
          </div>
          <div class="content-right">
            <span class="num"></span>
            <p class="title">{{$t('proCommunity.text7')}}</p>
          </div>
        </div>
        <p class="description">{{$t('proCommunity.text8')}}</p>
        <p class="description">{{$t('proCommunity.text9')}}</p>
      </div>
    </div>
    <div class="wrapper-pc">
      <div class="content-one">
        <div class="content-left">
          <img src="../assets/img/community/1.svg" />
        </div>
        <div class="content-right">
          <div class="pc">
            <span class="num"></span>
            <p class="title">{{$t('proCommunity.text7')}}</p>
            <div class="description" style="width: 50%; line-height: 1.8">{{$t('proCommunity.text8')}}</div>
          </div>
        </div>
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="content-two-mobile">
        <div class="num"></div>
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
          <div class="subTitle">{{$t('proCommunity.text17')}}！</div>
          <div class="btn" @click="openStart">{{$t('proCommunity.text18')}}</div>
        </div>
      </div>
    </div>
    <div class="wrapper-pc">
      <div class="content-two">
        <div class="num"></div>
        <div class="title">{{$t('proCommunity.text14')}}</div>
        <div class="description">{{$t('proCommunity.text15')}}</div>
        <div class="list-wrapper">
          <ul class="left-list">
            <li class="item">
              <img :src="leftList[0].imgUrl" />
              <p class="title">{{leftList[0].title}}</p>
              <p class="description">{{leftList[0].description}}</p>
            </li>
            <li class="item">
              <img :src="leftList[1].imgUrl" />
              <p class="title">{{leftList[1].title}}</p>
              <p class="description">{{leftList[1].description}}</p>
            </li>
            <li class="item">
              <img :src="leftList[2].imgUrl" />
              <p class="title">{{leftList[2].title}}</p>
              <p class="description">{{leftList[2].description}}</p>
            </li>
            <li class="item hasBorder">
              <img :src="leftList[3].imgUrl" />
              <p class="title">{{leftList[3].title}}</p>
              <p class="description">{{leftList[3].description}}</p>
            </li>
            <li class="other-li">
              <div class="subTitle">{{$t('proCommunity.text17')}}</div>
              <div class="btn" @click="openStart">{{$t('proCommunity.text18')}}</div>
            </li>
          </ul>
          <ul class="right-list">
            <li v-for="item in rightList" :key="item.index">
              <img :src="item.imgUrl" />
              <p class="title">{{item.title}}</p>
              <p class="description">{{item.description}}</p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

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
  created() {
    if (window.localStorage.getItem('secretLang') === 'EN') {
      this.isEN = true
    } else {
      this.isEN = false
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

<style lang="stylus" rel="stylesheet/stylus" scoped>
  &.cnPcHasLetter
    letter-spacing: 20px;
  &.enPcHasLetter
    letter-spacing: 8px;
  .wrapper
    .wrapper-top
      .top-content
        display flex
        flex-direction column
        justify-content flex-start
        padding-left 150px
        padding-top 220px
        width 100%
        height 880px
        background url("../assets/img/community/banner.png") no-repeat
        background-position center
        background-size cover
        .subTitle
          margin 110px 20px 30px 0
          display inline
          color #636e72
          font-weight bold
        .title
          font-size 52px
          color #2d3436
          font-weight bold
        .title-middle
          margin 26px 0 50px
        &.isHasLetter
          letter-spacing: 20px;
    .wrapper-top-mobile
      position relative
      width 100%
      height 334px
      background url("../assets/img/community/banner.png") no-repeat
      background-position center
      background-size contain
      .top-content
        position absolute
        display flex
        flex-direction column
        justify-content flex-start
        left 30px
        top 90px
        font-weight bold
        .subTitle
          display inline
          color #636e72
          font-size 14px
        .title
          font-weight bold
          margin-top 10px
          font-size 20px
          color #2d3436
        &.isMobileHasLetter
          letter-spacing: 5px;
    .banner-wrapper
      margin 0 auto
      width 1400px
      height auto
      position relative
      @media screen and (max-width: 1400px)
        width 100%
        padding 0 40px
      .banner
        z-index 2
        margin 0 auto
        width 1400px
        height 320px
        border-radius 5px
        background-color #fff
        display flex
        flex-direction column
        padding 40px 0 0 70px
        -moz-box-shadow 0px 0px 3px #333333
        -webkit-box-shadow 0px 0px 3px #333333
        box-shadow 0px 0px 3px #333333
        @media screen and (max-width: 1400px)
          width 100%
          padding 0 40px
        .num
          display block
          background url("../assets/img/product/01.svg") no-repeat
          width 24px
          height 16px
          background-size 24px 16px
          padding-bottom 20px
          border-bottom 3px solid #000
        .title
          margin-top 24px
          font-size 30px
          color #2d3436
        .description
          width 60%
          line-height 1.4
          margin-top 16px
          font-size 16px
          color #636e72
        .play
          cursor pointer
          user-select none
          margin-top 28px
          width 40px
          height 32px
          background url("../assets/img/product/play.svg") no-repeat
          background-size 40px 32px
      .banner-bg
        z-index -1
        position absolute
        width 630px
        height 140px
        background url("../assets/img/product/bg.png") no-repeat
        background-size 630px 140px
        right -5%
        bottom -70px
        background-position right
        @media (max-width: 1600px) {
          right: 0
        }
    .banner-wrapper-mobile
      position relative
      z-index 2
      width 100%
      background-color #fff
      padding-bottom 20px
      -moz-box-shadow 0px 0px 3px #ccc
      -webkit-box-shadow 0px 0px 3px #ccc
      box-shadow 0px 0px 3px #ccc
      @media (max-width: 768px) {
        width 90%
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
          background url("../assets/img/product/01.svg") no-repeat
          width 18px
          height 14px
          background-size 18px 14px
          padding-bottom 20px
          border-bottom 2px solid #000
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
          margin 40px 0 30px
        .description
          font-size 14px
          color #636e72
          line-height 2
        .play
          cursor pointer
          user-select none
          margin-top 20px
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
        flex-direction row
        align-items center
        .content-left
          width 50%
          margin-right 40px
          img
            width 100%
        .content-right
          flex 1
          display flex
          flex-direction column
          align-items flex-end
          .num
            display block
            background url("../assets/img/product/02.svg") no-repeat
            width 18px
            height 14px
            background-size 18px 14px
            padding-bottom 20px
            border-bottom 2px solid #000
          .title
            text-align right
            margin 20px 0
            font-size 16px
            color #2d3436
            font-weight bold
      .description
        font-size 14px
        color #636e72
        line-height 1.8
    .content-two-mobile
      margin 60px 30px 100px
      position relative
      @media screen and (max-width: 1200px)
        margin: 30px 10px 80px
      .num
        display block
        background url("../assets/img/product/03.svg") no-repeat
        width 18px
        height 14px
        background-size 18px 14px
        padding-bottom 20px
        border-bottom 2px solid #000
      .title
        margin 20px 0
        font-size 16px
        color #2d3436
        font-weight bold
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
        position absolute
        bottom 60px
        left 0
        .subTitle
          font-size 14px
          width 100%
          line-height 1.4
          font-weight bold
          color #2d3436
          @media (min-width: 414px) and (max-width: 580px) {
            width 60%
          }
          @media (min-width: 580px) and (max-width: 725px) {
            width 80%
          }
          @media (max-width: 414px) {
            width 49%
          }
        .btn
          font-size 14pxd
          margin-top 20px
    .content-one
      margin 230px auto
      padding 40px 70px
      width 1400px
      display flex
      flex-direction row
      @media screen and (max-width: 1400px)
        width 100%
        padding 0 40px
      .content-left
        width 50%
        img
          width 500px
          height 400px
      .content-right
        width 50%
        .pc
          width 100%
          height auto
          display flex
          flex-direction column
          align-items flex-end
          .num
            display block
            background url("../assets/img/product/02.svg") no-repeat
            width 24px
            height 16px
            background-size 24px 16px
            padding-bottom 20px
            border-bottom 3px solid #000
          .title
            margin-top 30px
            font-size 20px
            font-weight bold
            color #2d3436
          .description
            margin-top 40px
            font-size 14px
            color #636e72
    .content-two
      margin 160px auto
      padding 0 70px
      width 1400px
      @media screen and (max-width: 1400px)
        width 100%
        padding 0 40px
      .num
        display block
        background url("../assets/img/product/03.svg") no-repeat
        width 24px
        height 16px
        background-size 24px 16px
        padding-bottom 20px
        border-bottom 3px solid #000
      .title
        margin-top 30px
        font-size 20px
        font-weight bold
        color #2d3436
      .description
        margin-top 40px
        font-size 14px
        color #636e72
      .btn
        margin-top 52px
        cursor pointer
        user-select none
        font-size 16px
        color #2d3436
        text-align center
        line-height 56px
        height 56px
        width 200px
        border .5px solid #667070
      .list-wrapper
        margin-top 80px
        display flex
        flex-direction row
        .left-list
          width 50%
          margin-top 90px
          .item
            border 1px solid #c6c6c6
            border-right none
            border-bottom none
            padding-top 50px
            padding-left 30px
            height 330px
            .description
              width 95%
              line-height 1.6
          .hasBorder
            border-bottom 1px solid #c6c6c6
          .other-li
            height 330px
            .subTitle
              margin-top 52px
              font-size 24px
              width 70%
              font-weight bold
              color #2d3436
              line-height 60px
            .btn
              margin-top 20px
        .right-list
          width 50%
          li
            padding-top 50px
            padding-left 30px
            height 330px
            border 1px solid #c6c6c6
            border-bottom none
            &:last-child
              border-bottom 1px solid #c6c6c6
            .description
              width 95%
              line-height 1.6
</style>
