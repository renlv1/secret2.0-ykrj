<template>
  <div class="news-w">

    <div class="wrapper-pc">
      <div class="banner banner-m-t">
        <img :src="require(`@img/gif2/new/banner_${$lang}.svg`)" alt="">
        <div class="gif" :class="{'en-gif': $lang === 'en'}">
          <img src="@img/gif2/new/new.gif" alt="" class="gif-img">
        </div>
      </div>
    </div>

    <div class="wrapper-mobile">
      <div class="banner">
        <img :src="require(`@img/news/mobile_banner_${$lang}.svg`)" alt="">
      </div>
    </div>

    <div class="news-content-wrapper">
      <div class="news-content">
        <div class="top-t">
          <div class="text-new">NEWS</div>
          <div class="btn">
            <div class="a-t" :class="{'active-a': activeIndex === 1}" @click="switchIndex(1)">{{$t('news.text3')}}</div>
            <div class="a-t" :class="{'active-a': activeIndex === 0}" @click="switchIndex(0)">{{$t('news.text2')}}</div>
          </div>
        </div>
        <div class="mobile-c">
          <div class="text1-news">NEWS</div>
          <div class="a-c" :class="{'active-a': activeIndex === 1}" @click="switchIndex(1)">{{$t('news.text3')}}</div>
          <div class="a-c" :class="{'active-a': activeIndex === 0}" @click="switchIndex(0)">{{$t('news.text2')}}</div>
        </div>
        <ul class="news-uls-c">
          <li class="news-list-item" v-for="(item, index) in $t('newsData2')" :key="index" @click="gotoDetails(index)">
            <div class="img-c">
              <img :src="require('../assets/img/newPic2/news0' + index + '.jpg')" alt="" v-if="index < 8">
              <img :src="require('../assets/img/newPic2/news0' + index + '.svg')" alt="" v-if="index >= 8">
            </div>
            <div class="news-c-t">
              <div class="m-title" >{{item.text1}}</div>
              <div class="m-desc">{{item.text3}}</div>
              <div class="time">{{item.text2}}</div>
            </div>
            <div class="bg-t">
              <div class="btn-c">{{$t('news.text7')}}</div>
            </div>
          </li>
        </ul>
      </div>
    </div>

  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data() {
    return {
      activeIndex: 1,
      totalPage: 3,
      currentPage: 1,
      imgIndex: 1,
      newData: []
    }
  },
  created() {
    this.newData = this.$t('newsData').slice(0, 3)
  },
  methods: {
    switchIndex(index) {
      this.activeIndex = index
    },
    gotoDetails(index) {
      this.$router.push({
        path: '/newsDetails',
        query: {index}
      })
    },
    parentTurnPage(page) { // 页码
      this.imgIndex = (page - 1) * 3 + 1
      this.currentPage = page
      this.newData = this.$t('newsData').slice((page - 1) * 3, page * 3)
      // window.scrollTo(0, 0)
    },
    replaceString(str) {
      if (str) {
        // str = str.replace(/\n/g,"<br>")
        str = '<p>' + str.replace(/\n*$/g, '').replace(/\n/g, '</p> <p>') + '</p>'
        return str
      }
    }
  },
  components: {
    //vTurnPage: resolve => require(['@/components/turnPage.vue'], resolve)
  },
}
</script>

<style scoped lang="stylus">
  .banner-m-t{
    position: relative;
    .gif{
      position: absolute;
      right: 500px;
      top: 50%;
      transform: translateY(-50%);
      margin-top: -100px;
      &.en-gif{
        margin-top: 0
      }
      @media screen and (max-width: 1950px){
        right: 300px;
      }
      @media screen and (max-width: 1800px){
        right: 100px;
      }
      @media screen and (max-width: 1600px){
        width: 700px;
        right: 300px;
        margin-top: -50px
      }
      @media screen and (max-width: 1400px){
        right: 150px;
      }
    }
  }
  .cnPcHasLetter
    letter-spacing: 20px !important;

  .enPcHasLetter
    letter-spacing: 3px !important;

  .news-w
    .wrapper-pc
      .banner
        width: 100%
        background-color: #fff
        img
          display: block
          width: 100%
    .banner-v-c
      .text-w
        left: 100px
        transform translate(0, -50%)
        margin-left: 0
        @media screen and (max-width: 1200px)
          left: 10px
        .text2
          font-weight: bold
        .margi-text2
          margin: 10px 0
          @media screen and (max-width: 1200px)
            margin: 20px 0
        .wrap-p
          margin-left: 0
    .news-content-wrapper
      width 100%
      background-color: #FAFAFA
      .news-content
        width: 1200px
        margin: 0 auto
        @media screen and (max-width: 1200px)
          padding: 0
          width: 100%
        .top-t
          display: flex
          flex-direction column
          border-bottom: 1px solid #e8e5e5
          margin-bottom: 40px
          @media screen and (max-width: 1300px)
            margin-left: 30px
          @media screen and (max-width: 1200px)
            display: none
          .text-new
            font-size: 30px
            color #2d3436
            margin: 60px 0
            font-weight: bold
            @media screen and (max-width: 1200px)
              font-weight: bold
              display: none
          .btn
            margin-top 35px
            display flex
            flex-direction row
            .a-t
              font-size: 16px
              color #dfe6e9
              margin-right: 80px
              cursor pointer
              padding-bottom: 20px
              font-weight: bold
              &.active-a
                color #000
                border-bottom 2px solid #000
        .mobile-c
          display: none
          @media screen and (max-width: 1200px)
            display: flex
            align-items center
            padding: 26px 0 26px 0
            margin: 0 10px 16px 10px
            border-bottom: 1px solid #e8e5e5
          .text1-news
            font-size: 16px
            font-weight: bold
            color #2d3436
          .a-c
            font-size: 14px
            color #dfe6e9
            font-weight: bold
            margin-left: 40px
            &.active-a
              color #636e72
        .news-uls-c
          width: 100%
          display: flex
          align-items center
          justify-content center
          flex-wrap wrap
          padding-bottom: 140px
          margin: 0 auto
          @media screen and (max-width: 1200px)
            padding-bottom: 0
            justify-content flex-start
          .news-list-item
            width: 360px
            height: 380px
            margin-bottom: 60px
            position: relative
            cursor pointer
            transform translateY(0)
            transition all .3s linear
            @media screen and (max-width: 1400px)
              margin-bottom: 40px
            @media screen and (max-width: 1300px)
              margin-bottom: 20px
            @media screen and (max-width: 1200px)
              width: 50%
              height auto
              padding: 0 10px
              margin: 0 0 20px 0 !important
            &:nth-child(3n - 1)
              margin: 0 60px 60px 60px
              @media screen and (max-width: 1400px)
                margin: 0 40px 40px 40px
              @media screen and (max-width: 1300px)
                margin: 0 20px 20px 20px
            &:hover
              transform translateY(-5px)
              @media screen and (max-width: 1200px)
                transform translateY(0)
              .bg-t
                opacity: 1
                display: flex
                background-color: rgba(0, 0, 0, .6)
                @media screen and (max-width: 1200px)
                  display: none
            .img-c
              width: 100%
              height: 191px
              @media screen and (max-width: 1200px)
                height: 110px
              @media screen and (max-width: 500px)
                height: 87px
              img
                width: 100%
                height: 100%
            .news-c-t
              padding: 30px 30px 20px 30px
              background-color: #f4f4f4
              @media screen and (max-width: 1200px)
                padding: 10px
            .m-title
              font-size: 16px
              color #000
              height: 42px
              font-weight: bold
              @media screen and (max-width: 1200px)
                font-size: 13px
                height: 60px
              &.en-title
                font-size: 12px
            .m-desc
              font-size: 14px
              color #000
              margin: 20px 0
              overflow: hidden;
              text-overflow: ellipsis;
              display: -webkit-box;
              -webkit-box-orient: vertical;
              -webkit-line-clamp: 2;
              @media screen and (max-width: 1200px)
                margin: 10px 0
                -webkit-line-clamp: 3;
            .time
              font-size: 14px
              color #999
            .bg-t
              position: absolute
              left: 0
              top: 0
              width: 100%
              height: 100%
              background-color: #fff
              align-items center
              justify-content center
              display: flex
              opacity: 0
              transition all .3s linear
              @media screen and (max-width: 1200px)
                transition none
                z-index: -1
              .btn-c
                width: 250px
                height: 60px
                display: flex
                align-items center
                justify-content center
                border: 1px solid #fff
                font-size: 14px
                color #fff
        .turn-page-w
          border-top: 1px solid #e8e5e5
          padding-top: 40px
          margin-bottom: 100px
</style>
