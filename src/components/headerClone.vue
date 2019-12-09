<template>
  <div class="header-wrap">
    <div class="header wrap">
      <router-link tag="div" class="logo-box" to="/">
        <img src="~@img/common/logo_white.svg" height="25px" alt="">
      </router-link>
      <div class="head-nav">
        <li v-for="(item,index) in nav" :key="index" :class="{'has-child': item.child}" @click="gotoPath(item.path)">
          <!-- <a v-if="item.outside" target="_blank" :href="item.path" class="text"><span class="info-text">{{item.name}}</span></a> -->
          <router-link excat :to="item.path" class="text">
            <span class="info-text">{{item.text}}</span>
            <div class="child" v-if="item.child" @click.stop>
              <router-link :to="childItem.path" excat v-for="(childItem, i) in item.child" :key="i">
                {{childItem.text}}
              </router-link>
            </div>
          </router-link>
        </li>
        <li class="switch-lang">
          <span :class="{active: $lang === 'en'}" @click="switchLang('EN')">EN</span>
          <span style="margin: 0 5px">/</span>
          <span :class="{active: $lang === 'ko'}" @click="switchLang('KO')">KO</span>
          <span style="margin: 0 5px">/</span>
          <span :class="{active: $lang === 'cn'}" @click="switchLang('CN')">CN</span>
        </li>
        <li>
          <router-link class="text" to="/login">{{$t('header.text20')}}</router-link>
        </li>
      </div>
    </div>
    <!-- 移动端-->
    <div class="mobile-header">
      <router-link tag="div" class="logo-box" to="/">
        <img src="~@img/common/logo_mobile.svg" height="25px" alt="">
      </router-link>
      <div class="right">
        <div class="login" @click="$router.push('/login')">{{$t('header.text20')}}</div>
        <div class="right-menu" :class="{'close-menu': isShowMenu}" @click="isShowMenu = !isShowMenu"></div>
      </div>
    </div>
    <!-- 菜单-->
    <div class="show-menu" :class="{'menu-active': isShowMenu}">
      <ul class="uls" @click="isShowMenu = false">
        <li v-for="(item,index) in nav" :key="index" :class="{'has-child': item.child}">
          <router-link excat :to="item.path" tag="div" class="text"
                       :class="{'router-link-exact-active': isRoute === index}" @click.native="getRoA(index)">
            {{item.text}}
          </router-link>
          <dl class="child" v-if="item.child">
            <dd v-for="child in item.child" :key="child.text">
              <router-link :to="child.path" @click.native="getRo(index)">{{child.text}}</router-link>
            </dd>
          </dl>
        </li>
        <li class="lang-w">
          <span @click="switchLang('EN')" :class="{active: $lang === 'en'}">EN</span> /
          <span @click="switchLang('KO')" :class="{active: $lang === 'ko'}">KO</span> /
          <span @click="switchLang('CN')" :class="{active: $lang === 'cn'}">CN</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShowMenu: false,
      isRoute: -1,
      nav: [
        {
          text: this.$t('header.text1'),
          path: '/'
        },
        {
          text: this.$t('header.text2'),
          path: '/productSecret',
          child: [
            {
              text: 'Secret',
              path: '/productSecret'
            },
            {
              text: this.$t('header.text3'),
              path: '/proCommunity'
            }
          ]
        },
        {
          text: this.$t('header.text4'),
          path: '/artificial',
          child: [
            {
              text: this.$t('header.text5'),
              path: '/artificial'
            }
          ]
        },
        {
          text: this.$t('header.text7'),
          path: '/tradingCenter'
        },
        {
          text: this.$t('header.text9'),
          path: '/news'
        },
        {
          text: this.$t('header.text10'),
          path: '/about'
        },
        {
          text: this.$t('header.text11'),
          path: '/help'
        },
      ]
    }
  },
  created() {
    if (this.$route.path === '/tecBlock') {
      this.isRoute = 2
    } else if (this.$route.path === '/proCommunity') {
      this.isRoute = 1
    }
  },
  methods: {
    getRo(index) {
      this.isRoute = index
      console.log(index)
    },
    getRoA(index) {
      this.isRoute = -1
    },
    switchLang(lang) {
      window.localStorage.setItem('secretLang', lang)
      window.location.reload()
    },
    gotoPath(path) {
      if (this.$route.path !== path) {
        this.$router.push(path)
      }
    }
  }
}
</script>

<style lang="less" scoped>
  @blue: #0080f4;
  .has-child .child{
    @media screen and (max-width: 1200px){
      margin-left: 20px;
    }
  }

  .lang-w {
    text-align: center;
    margin-top: 20px;
    @media screen and (max-width: 330px) {
      margin-top: 0;
    }
    span {
      padding: 0 10px;
      &.active {
        color: @blue;
      }
    }
  }

  .header-wrap {
    font-size: 18px;
    position: fixed;
    width: 100%;
    left: 0;
    top: 0;
    z-index: 999;
    background-color: rgba(12, 17, 26, .4);
    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 88px;
      transition: .3s;
      width: 1200px;
      margin: 0 auto;
      @media screen and (max-width: 1200px) {
        display: none;
      }
      @media screen and (max-width: 1400px) {
        width: 100%;
        padding: 0 20px;
      }
      .logo-box {
        cursor: pointer;
        img {
          vertical-align: top;
        }
      }
      .head-nav {
        height: 100%;
        line-height: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        li {
          transition: .3s;
          cursor: pointer;
          position: relative;
          text-align: center;
          color: #fff;
          width: auto;
          padding: 0 25px;
          font-size: 15px;
          height: 100%;
          display: flex;
          align-items: center;
          .text {
            //display: block;
            position: relative;
            width: 100%;
            /*height: 100%;*/
            /*display: flex;*/
            /*align-items: center;*/
            /*justify-content: center;*/
            &:after {
              content: '';
              display: block;
              position: absolute;
              width: 0;
              height: 100%;
              background-color: transparent;
              border-bottom: 2px solid transparent;
              top: 0;
              bottom: 0;
              right: 0;
              left: 0;
              transition: width .4s ease-in-out;
            }
            &.router-link-exact-active {
              color: @blue;
            }
            .info-text {
              display: inline-flex;
              line-height: 1.2;
            }
          }
          &.has-child .text:after {
            content: '';
            display: inline-block;
            border: 5px solid transparent;
            border-top-color: #fff;
            vertical-align: middle;
            margin-left: 10px;
            left: auto;
            right: -15px;
            top: 5px;
            bottom: auto;
          }
          &:hover {
            color: @blue;
            .child {
              opacity: 1;
              top: 35px;
              visibility: visible;
              transition: .3s .1s;
            }
            .text:after {
              border-top-color: @blue !important;
            }
          }
          &:last-child {
            padding-right: 0;
            .text {
              line-height: 36px;
              height: 36px;
              border: 1px solid @blue;
              border-radius: 20px;
              padding: 0 25px;
              color: @blue;
              transition: .5s;
              &:hover {
                background: @blue;
                color: #fff;
              }
            }
          }
        }
        .child {
          position: absolute;
          opacity: 0;
          width: 200px;
          text-align: left;
          left: -10px;
          top: 20px;
          line-height: 30px;
          visibility: hidden;
          background: rgba(255, 255, 255, 0.3);
          box-shadow: 0 2px 5px rgba(9, 131, 239, .15);
          padding: 10px 0;
          a {
            display: block;
            padding: 10px 30px;
            color: #fff;
            &:hover {
              color: @blue;
            }
          }
          &.hide {
            visibility: hidden !important;
            transition: none !important;
          }
        }
      }
      .switch-lang {
        color: #fff !important;
        cursor: auto !important;
        span {
          cursor: pointer;
        }
        span.active {
          color: @blue !important;
        }
      }
    }
    .nav-mask {
      position: fixed;
      width: 100%;
      height: 100%;
      left: 0;
      top: 0;
      z-index: 999;
    }
    .mobile-header {
      height: 70px;
      position: fixed;
      top: 0;
      width: 100%;
      background: #fff;
      box-shadow: 0 0 5px rgba(0, 0, 0, .2);
      @media screen and (max-width: 1200px) {
        display: block;
      }
      @media screen and (min-width: 1200px) {
        display: none;
      }
      .logo-box {
        height: 46px;
        cursor: pointer;
        display: flex;
        align-items: center;
        padding-left: 20px;
        position: absolute;
        left: 0;
        top: 50%;
        transform: translateY(-50%);
        img {
          width: 150px;
        }
      }
      .right {
        position: absolute;
        right: 0;
        top: 50%;
        transform: translateY(-50%);
        z-index: 100002;
        padding: 10px 20px 10px 10px;
        cursor: pointer;
        display: flex;
        align-items: center;
        .login {
          width: 80px;
          height: 30px;
          display: flex;
          align-items: center;
          justify-content: center;
          border-radius: 15px;
          margin-right: 10px;
          border: 1px solid #0080f4;
          color: #0080f4;
          @media screen and (max-width: 330px) {
            width: 60px;
          }
        }
        .right-menu {
          width: 24px;
          height: 22px;
          background: url("../assets/img/common/nav.svg") no-repeat center / cover;
          &.close-menu {
            background: url("../assets/img/common/nav_close.svg") no-repeat center / cover;
            width: 20px;
            height: 20px;
          }
        }
      }
    }
    .show-menu {
      background-color: rgba(255, 255, 255, .98);
      overflow: hidden;
      max-height: 0;
      transition: max-height .3s linear;
      display: none;
      position: fixed;
      top: 70px;
      width: 100%;
      box-shadow: 0 3px 10px rgba(0, 0, 0, .15);
      z-index: 98;
      @media screen and (max-width: 1200px) {
        display: block;
      }
      &.menu-active {
        max-height: 100%;
      }
      .uls {
        border-top: 1px solid @blue;
        padding: 10px 0 40px;
        min-height: 100vh;
        li {
          padding: 0 36px;
          line-height: 50px;
          @media screen and (max-width: 400px) {
            line-height: 40px;
          }
        }
        a {
          display: block;
          font-size: 14px;
        }
        .router-link-exact-active {
          color: @blue;
        }
      }
    }
    .lang {
      display: flex;
      align-items: center;
      padding-top: 10px;
      span {
        margin-right: 22px;
      }
      img {
        width: 24px;
        margin-right: 8px;
      }
    }
  }
</style>
