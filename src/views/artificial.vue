<template>
  <div class="wrap-ai">
    <div class="wrapper-pc">
      <div class="banner banner-m-t">
        <img :src="require(`@img/gif2/artificial/banner_${$lang}.svg`)" alt="" class="img-c-m">
        <div class="gif">
          <img src="@img/gif2/artificial/artificial.gif" alt="" class="gif-img">
        </div>
      </div>
    </div>
    <div class="wrapper-pc">
      <div class="main">
        <div class="no-a">
          <div class="title">
            <div class="bor-l"></div>
            <div class="w-c-t">
              <div class="icon">
                <img src="../assets/img/borderNumber/01.svg" alt="">
              </div>
              <div class="tit">{{$t('tecIntel.text3')}}</div>
            </div>
            <div class="bor-l" style="opacity: 0;"></div>
          </div>
          <div class="list">
            <div class="li" v-for="(item, index) in $t('tecIntel.aiTechnique')" :key="index">
              <div class="info-box" :class="{'t-en': $i18n.locale === 'EN', 'ko-t': $i18n.locale === 'KO' && index === 3}">
                <div class="tit">{{item.tit}}</div>
                <div class="img"><img :src="item.img" alt=""></div>
                <div class="con">{{item.text}}</div>
              </div>
            </div>
          </div>
        </div>
        <div class="no-b">
          <div class="icon">
            <img src="../assets/img/borderNumber/02.svg" alt="">
          </div>
          <div class="title">{{$t('tecIntel.text4')}}</div>
          <div class="list">
            <div class="li" v-for="(item,index) in $t('tecIntel.listTwo')" :key="index">
              <div class="img"><img :src="item.img" alt=""></div>
              <div class="tit"><i class="iocn"><img :src="item.icon" alt=""></i> <span class="text">{{item.tit}}</span></div>
              <p class="text-p">{{item.text}}</p>
            </div>
          </div>
        </div>
        <div class="footer">
          <div class="title">{{$t('tecIntel.text11')}}</div>
          <div class="add-secret" @click="download">{{$t('tecIntel.text12')}}</div>
        </div>
      </div>
    </div>

    <div class="wrapper-mobile">
      <div class="banner">
        <img :src="require(`@img/intel/mobile_banner_${$lang}.svg`)" alt="">
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="banner-wrapper-mobile">
        <div class="top">
          <div class="line"></div>
          <div class="num">
            <img src="../assets/img/home/01.svg" alt="">
          </div>
          <div class="title">{{$t('tecIntel.text3')}}</div>
        </div>
        <div class="ul-wrapper">
          <ul>
            <li v-for="(item) in $t('tecIntel.aiTechnique')" :key="item.index">
              <span class="title">{{item.tit}}</span>
              <img :src="item.img" />
              <p class="description">{{item.text}}</p>
            </li>
          </ul>
          <div class="banner-bg"></div>
        </div>
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="top-mobile">
        <span class="line"></span>
        <span class="num">
          <img src="../assets/img/home/02.svg" alt="">
        </span>
        <p class="title">{{$t('tecIntel.text4')}}</p>
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="content-one-mobile">
        <div class="box">
          <div class="img-box">
            <img src="../assets/img/intel/a.png" />
          </div>
          <div class="content-box">
            <div class="box-top">
              <img src="../assets/img/ai/bule-icon.svg"/>
              <p class="title">{{$t('tecIntel.text6')}}</p>
            </div>
            <p class="description">{{$t('tecIntel.text7')}}</p>
          </div>
        </div>
        <div class="box">
          <div class="img-box">
            <img src="../assets/img/intel/b.png" />
          </div>
          <div class="content-box">
            <div class="box-top">
              <img src="../assets/img/ai/red-icon.svg"/>
              <p class="title">{{$t('tecIntel.text9')}}</p>
            </div>
            <p class="description">{{$t('tecIntel.text10')}}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="wrapper-mobile">
      <div class="content-two-mobile">
        <p class="description">{{$t('tecIntel.text11')}}</p>
        <div class="btn-wrapper" :class="{'ko-btn': $i18n.locale === 'KO'}">
          <div class="btn" @click="join">{{$t('tecIntel.text12')}}</div>
          <div class="line"></div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        aiTechnique: [
          {
            tit: '深度学习算法',
            img: require('../assets/img/ai/li-1.svg'),
            text: '机器人对话更加智能化，拟人化',
          },
          {
            tit: '自然语言处理',
            img: require('../assets/img/ai/li-2.svg'),
            text: '多轮智能对话，上下语境理解',
          },
          {
            tit: '大数据技术',
            img: require('../assets/img/ai/li-3.svg'),
            text: '行业对话场景的大数据应用',
          },
          {
            tit: '人机交互技术',
            img: require('../assets/img/ai/li-4.svg'),
            text: '智能人机交互，给社交带来无尽可能',
          },
          {
            tit: '深度强化学习',
            img: require('../assets/img/ai/li-5.svg'),
            text: '深度学习技术和神经网络，解决更多难题',
          },
          {
            tit: '文字识别',
            img: require('../assets/img/ai/li-6.svg'),
            text: '自然场景下区域检测的文字识别技术',
          }
        ],
        listTwo: [
          {
            img: require('../assets/img/ai/li-a.jpg'),
            icon: require('../assets/img/ai/bule-icon.svg'),
            tit: '复制数据，延续灵魂',
            text: '采用区块链的技术存放和运行人类数据，制造出另一个你。',
          },
          {
            img: require('../assets/img/ai/li-b.jpg'),
            icon: require('../assets/img/ai/red-icon.svg'),
            tit: '脑机结合，转化意识',
            text: '人脑与数字世界连接,大脑皮层产生的指令,最终会传递到数字世界中,而数字信号将把指令传递给自动化机械和系统。',
          }
        ],
      }
    },
    components: {},
    created() {
    },
    mounted() {
    },
    methods: {
      join() {
        this.$router.push('/about')
      },
      download() {
        window.open('https://isecret.im/', '_blank');
      }
    }
  }
</script>

<style lang="less" rel="stylesheet/less" scoped>
@bc: #fff;
@mb: #d3d3d3;
@title: #000;
@tit: #2d3436;
@con: #636e72;
@bor-color: #0080f4;
@but-text: #0c111a;
@title-size: 30px;
@tit-size: 20px;
@fs16: 16px;
@fs14: 14px;
@text-color: #59687c;
.banner-m-t{
  position: relative;
  .gif{
    position: absolute;
    right: 500px;
    top: 30%;
    text-align: center;
    @media screen and (max-width: 1950px){
      right: 300px;
      top: 27%;
    }
    @media screen and (max-width: 1800px){
      right: 200px;

    }
    @media screen and (max-width: 1700px){
      right: 300px;
      .gif-img{
        width: 470px;
      }
    }
    @media screen and (max-width: 1600px){
      width: 500px;
      right: 200px;
    }
    @media screen and (max-width: 1450px){
      right: 200px;
      .gif-img{
        width: 380px;
      }
    }
  }
}
.line-h{
  line-height: 1.5;
}
.wrap-ai{
   width: 100%;
  .banner{
    width: 100%;
    img{
      width: 100%;
    }
  }
  .main{
    width: 100%;
    .no-a{
      width: 100%;
      background: url("../assets/img/ai/BG.png") no-repeat center / cover;
      padding-bottom: 80px;
      padding-top: 100px;
      .w-c-t{
        width: 1000px;
        display: flex;
        align-items: center;
        @media screen and (max-width: 1200px){
          margin: 0 auto;
        }
      }
      .title{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: flex-start;
        .bor-l{
          flex: 1;
          height: 1px;
          background-color: @tit;
          margin-right: 20px;
        }
        .icon{
          margin-right: 25px;
        }
        .tit{
          font-size: @title-size;
          color: @tit;
        }
      }
      .list{
        width: 1000px;
        margin: 0 auto;
        //background: url("../assets/img/ai/BG.png") no-repeat center;
        background-size: contain;
        display: flex;
        align-items: center;
        flex-flow: wrap;
        justify-content: space-between;
        margin-top: 58px;
        position: relative;
        z-index: 10;
        &:after{
          display: block;
          width: 630px;
          height: 135px;
          position: absolute;
          right: -80px;
          bottom: 20px;
          content: '';
          z-index: -1;
          background: url(../assets/img/ai/bg_2.png) no-repeat center;
          background-size: contain;
          @media screen and (max-width: 1400px){
            right: 0;
          }
        }
        .li{
          width: 280px;
          height: 320px;
          background-color: @bc;
          /*box-shadow: 0 0 6px 3px rgba(0,0,0, .1);*/
          box-shadow: 0 0 6px 3px rgba(153, 153, 153, .1);
          display: flex;
          align-items: center;
          text-align: center;
          margin-bottom: 70px;
          &:nth-child(2){
            margin-bottom: 100px;
          }
          &:nth-child(5){
            margin-bottom: 100px;
          }
          .info-box{
            width: 229px;
            height: 100%;
            padding: 70px 0;
            margin:  0 auto;
            &.t-en{
              padding: 43px 0;
            }
            &.ko-t{
              .tit{
                width: 80%;
                margin: 0 auto;
              }
              .img{
                margin: 30px auto;
              }
            }
            .tit{
              font-size: @tit-size;
              color: @tit;
            }
            .img{
              width: 60px;
              height: 60px;
              margin: 44px auto 36px;
              img{
                width: 100%;
                height: 100%;
              }
            }
            .con{
              font-size: @fs14;
              color: @text-color;
              .line-h;
            }
          }
        }
      }
    }
    .no-b{
      width: 100%;
      height: 840px;
      padding-top: 92px;
      background: #FAFAFA url("../assets/img/ai/c-bg.jpg") no-repeat center / cover;
      .icon{
        margin: 0 auto 40px;
        text-align: center;
      }
      .title{
        font-size: @tit-size;
        color: @tit;
        text-align: center;
        padding-bottom: 80px;
      }
      .list{
        width: 1100px;
        height: 460px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 0 auto;
        .li{
          background-color: #fff;
          width: 500px;
          height: 100%;
          border: 1px solid #e8e7e7;
          .img{
            width: 100%;
            height: 280px;
            img{
              width: 100%;
              height: 100%;
            }
          }
          .tit{
            width: 100%;
            font-size: @tit-size;
            padding: 40px 24px 20px 24px;
            color: @tit;
            display: flex;
            align-items: center;
            .iocn{
              display: inline-block;
              width: 23px;
              height: 23px;
              margin-right: 10px;
              vertical-align: middle;
              img{
                width: 100%;
                height: 100%;
              }
            }
            .text{
              font-size: @fs16;
              color: @con;
              .line-h;
            }
          }
          .text-p{
            padding: 0 24px;
            .line-h;
            font-size: 14px;
            color: @con;
          }
        }
      }
    }
    .footer{
      width: 100%;
      height: auto;
      padding-bottom: 100px;
      .title{
        font-size: 40px;
        color: @bor-color;
        text-align: center;
        padding: 120px 0 60px;
        max-width: 1300px;
        margin: 0 auto;
        padding-left: 50px;
      }
      .add-secret{
        width: 250px;
        height: 60px;
        line-height: 60px;
        text-align: center;
        font-size: @fs14;
        color: @tit;
        background-size: @bc;
        border: 1px solid @bor-color;
        margin: 0 auto;
        cursor: pointer;
        transition: all .4s linear;
        &:hover{
          background-color: @bor-color;
          color: #fff;
        }
      }
    }
  }
}
</style>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .num
    img
      display: block
  .wrapper-top-mobile
    position relative
    width 100%
    height 334px
    background url("../assets/img/intel/banner.png") no-repeat
    background-position center
    background-size contain
    .top-content
      position absolute
      display flex
      flex-direction column
      justify-content flex-start
      left 30px
      top 108px
      .subTitle
        display inline
        font-weight bold
        color #636e72
        font-size 12px
      .title-middle
        margin 7px 0 10px
      .title
        font-weight bold
        font-size 20px
        color #2d3436
      &.cnMobileHasLetter
        letter-spacing 3px
      &.enMobileHasLetter
        letter-spacing: 0;
        width 70%
  .banner-wrapper-mobile
    margin 0 15px 0
    .top
      display flex
      align-items center
      .line
        width 20px
        height 1px
        background-color #636e72
      .num
        margin 0 10px
        height: 16px
        display: flex
        align-items center
        justify-content center
        img
          display: block
      .title
        width 75%
        font-size 16px
        color #2d3436
        font-weight bold
        line-height: 1
    .ul-wrapper
      position relative
      height auto
      z-index 2
      ul
        margin-top 50px
        display flex
        flex-direction row
        justify-content space-between
        flex-wrap wrap
        li
          width 46%
          margin-bottom 20px
          padding-bottom 10px
          display flex
          flex-direction column
          align-items center
          -moz-box-shadow 0px 0px 3px #ccc
          -webkit-box-shadow 0px 0px 3px #ccc
          box-shadow 0px 0px 3px #ccc
          background-color #fff
          .title
            margin-top 40px
            font-size 18px
            font-weight bold
            color #2d3436
            text-align center
          img
            display block
            margin 15px auto 20px
            width 50%
            @media (max-width: 767px) {
              width 30%
            }
          .description
            text-align center
            font-size 14px
            color #2d3436
            width 80%
            line-height 1.6

      .banner-bg
        z-index -1
        position absolute
        width 80%
        height 70px
        background url("../assets/img/product/bg.png") no-repeat
        background-size cover
        right 10%
        bottom -20px
  .top-mobile
    display flex
    flex-direction row
    align-items center
    margin 60px 0 30px 30px
    .line
      width 20px
      height 1px
      background-color #636e72
    .num
      margin 0 10px
      height: 16px
      display: flex
      align-items center
      justify-content center
    .title
      width 75%
      font-size 16px
      color #2d3436
      font-weight bold
      line-height: 1
  .content-one-mobile
    .box
      margin 0 30px 40px
      padding-bottom 20px
      -moz-box-shadow 0px 0px 3px #ccc
      -webkit-box-shadow 0px 0px 3px #ccc
      box-shadow 0px 0px 3px #ccc
      .img-box
        img
          width 100%
      .content-box
        padding 0 20px
        background-color #fff
        width 100%
        .box-top
          margin 18px 0 10px
          display flex
          flex-direction row
          align-items center
          .title
            margin-left 8px
            font-size 20px
            font-weight bold
            color #2d3436
        .description
          font-size 12px
          color #636e72
          line-height 1.6
  .content-two-mobile
    margin 60px 30px
    .description
      width 95%
      font-weight bold
      font-size 20px
      line-height 1.6
      color #0080f4
    .btn-wrapper
      margin-top 30px
      width 100px
      height 30px
      position relative
      &.ko-btn,&.ko-btn .btn
        width: 150px
      .btn
        cursor pointer
        user-select none
        font-size 14px
        color #2d3436
        text-align center
        line-height 30px
        height 30px
        width 100px
        border 1px solid #0080f4
      .line
        position absolute
        top 50%
        right -45px
        width 60px
        height 1px
        background-color #2d3436
</style>
