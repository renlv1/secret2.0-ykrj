<template>
  <div class="footer">
    <div class="footer-w">
      <div class="left">
        <p class="text1">{{$t('header.text12')}}</p>
        <p class="text2" v-html="$t('header.text13')"></p>
        <ul class="uls">
          <li class="links-lis"><router-link to="/">{{$t('header.text1')}}</router-link></li>
          <li class="links-lis"><router-link to="/productSecret">{{$t('header.text2')}}</router-link></li>
          <li class="links-lis"><router-link to="/artificial">{{$t('header.text4')}}</router-link></li>
          <li class="links-lis"><router-link to="/tradingCenter">{{$t('header.text7')}}</router-link></li>
          <li class="links-lis"><router-link to="/news">{{$t('header.text9')}}</router-link></li>
          <li class="links-lis"><router-link to="/about">{{$t('header.text10')}}</router-link></li>
          <li class="links-lis"><router-link to="/help">{{$t('header.text11')}}</router-link></li>
        </ul>
        <div class="friend-link friend-link-pc">
          <a target="_blank" href="https://www.pksport.ai/" class="friend">
            <img src="../assets/img/common/pk.png" alt="">
            <span>PK</span>
          </a>
          <a target="_blank" href="https://kleingame.ai/#/newExchange" class="friend">
            <img src="../assets/img/common/klien.png" alt="">
            <span>{{$t('header.text24')}}</span>
          </a>
        </div>
        <p class="copyright">© Secret 2018 All Rights Reserved</p>
      </div>
      <div class="right">
        <div class="btn-w">
          <div class="btn-item">
            <div class="a">{{$t('header.text14')}}</div>
          </div>
        </div>
        <div class="icon-w">
          <a target="_blank" title="facebook" href="https://www.facebook.com/pg/secretworth/posts/?ref=page_internal" class="icon"><img width="40px" src="../assets/img/iconLink/facebook.png" alt=""></a>
          <a target="_blank" title="twitter" href="https://twitter.com/Secret77675343" class="icon"><img width="40px" src="../assets/img/iconLink/twitter.png" alt=""></a>
          <a target="_blank" title="instagram" href="https://www.instagram.com/" class="icon"><img width="40px" src="../assets/img/iconLink/instagram.png" alt=""></a>
          <a target="_blank" title="linkedin" href="https://www.linkedin.com/login?fromSignIn=true&trk=guest_homepage-basic_nav-header-signin" class="icon"><img width="40px" src="../assets/img/iconLink/linkedIn.png" alt=""></a>
          <a target="_blank" title="snapchat" href="https://accounts.snapchat.com/accounts/welcome" class="icon"><img width="40px" src="../assets/img/iconLink/snapchat.png" alt=""></a>
        </div>
      </div>
      <div class="mobile">
        <ul class="uls">
          <li class="links-lis"><router-link to="/">{{$t('header.text1')}}</router-link></li>
          <li class="links-lis"><router-link to="/productSecret">{{$t('header.text2')}}</router-link></li>
          <li class="links-lis"><router-link to="/artificial">{{$t('header.text4')}}</router-link></li>
          <li class="links-lis"><router-link to="/tradingCenter">{{$t('header.text7')}}</router-link></li>
          <li class="links-lis"><router-link to="/news">{{$t('header.text9')}}</router-link></li>
          <li class="links-lis"><router-link to="/about">{{$t('header.text10')}}</router-link></li>
          <li class="links-lis"><router-link to="/help">{{$t('header.text11')}}</router-link></li>
        </ul>
        <div class="friend-link">
          <a target="_blank" href="https://www.pksport.ai/" class="friend">
            <img src="../assets/img/common/PK.svg" alt="">
            <span>PK</span>
          </a>
          <a target="_blank" href="https://kleingame.ai/#/newExchange" class="friend">
            <img src="../assets/img/common/klien.svg" alt="">
            <span>{{$t('header.text24')}}</span>
          </a>
        </div>
        <p class="copyright">© Secret 2018 All Rights Reserved</p>
      </div>
    </div>
  </div>

</template>

<script type="text/ecmascript-6">
	export default {
		data() {
			return {
        pdfUrl: ''
      }
		},
    created() {
		  let url = 'https://www.secretworth.com'
      if (window.localStorage.getItem('secretLang') === 'EN') {
        this.pdfUrl = url + '/pdf/white_en.pdf'
      } else {
        this.pdfUrl = url + '/pdf/white.pdf'
      }
    }
	}
</script>

<style scoped lang="stylus">
.footer
  background-color: #0080f4
.footer-w
  width: 1300px
  margin 0 auto
  display: flex
  justify-content space-between
  padding: 50px
  color #86c3fa
  @media (max-width: 1400px) {
    width: 100%;
    padding: 40px;
    margin: 0 auto;
  }
  .friend-link
    display: flex
    align-items center
    margin-bottom: 12px
    @media screen and (min-width: 1200px)
      display: flex
    .friend
      display: flex
      align-items center
      margin-right: 40px
      font-size: 12px
      color rgba(255,255,255,.4)
      img
        margin-right: 6px
  .friend-link-pc
    @media screen and (min-width: 1200px)
      display: flex
    @media screen and (max-width: 1200px)
      display: none
  .left
    .text1
      font-size: 20px
      font-weight bold
      color #fff
    .text2
      margin-top: 20px
      font-size: 14px
      color #fff
      line-height: 1.9
      max-width 700px
    .uls
      display: flex
      align-items center
      margin: 35px 0 30px
      .links-lis
        &:nth-child(1)
          a
            padding-left: 0
        &:last-child
          a
            margin-right: 0
        a
          padding: 10px
          transition .3s
          &:hover
            color: #fff
          font-size: 14px
          margin-right: 40px
          @media screen and (max-width: 1500px)
            margin-right: 20px
    .copyright
      font-size: 14px
  .right
    .btn-w
      display: flex
      justify-content flex-end
      .btn-item .a
        // cursor pointer
        width: 250px
        height: 60px
        border: 1px solid #fff
        display: flex
        align-items center
        justify-content center
        border-radius 2px
        color #fff
        font-size: 14px
    .icon-w
      display: flex
      align-items center
      justify-content flex-end
      padding-top 56px
      .icon
        margin-left: 50px
    .logo
      float: right
      a
        display: block
  @media screen and (min-width: 1200px)
    .mobile
      display none
  @media screen and (max-width: 1200px)
    width 100%
    display block
    padding 40px 15px;
    .copyright
      font-size 13px
    .uls
      display flex
      flex-wrap wrap
      font-size 13px
      margin-bottom 30px
      li
        margin-right 10px
        margin-bottom: 10px
    .mobile
      display block
    .left
      .uls, .copyright
        display none
      .text2
        max-width none
    .right
      .btn-w
        display: block
        .btn-item .a
          cursor pointer
          width: 170px
          height: 40px
          border: 1px solid #fff
          display: flex
          align-items center
          justify-content center
          border-radius 2px
          color #fff
          font-size: 14px
          margin-top 40px
      .icon-w
        display: flex
        align-items center
        justify-content flex-start
        padding 26px 0
        .icon
          margin: 0 20px 0 0
.mobile-footer
  background-color: #2d3436
  padding: 80px 50px 60px 50px
  @media screen and (max-width: 1200px)
    display: block
  @media screen and (min-width: 1200px)
    display: none
  @media screen and (max-width: 750px)
    padding: 50px 10px
  .text1
    font-size: 24px
    color #fff
    @media screen and (max-width: 750px)
      font-size: 16px
  .text2
    font-size: 18px
    color #fff
    line-height: 2
    margin: 20px 0 40px
    @media screen and (max-width: 750px)
      font-size: 12px
  .btn-w
    display: flex
    align-items center
    .btn-item .a
      cursor pointer
      width: 250px
      height: 60px
      border: 1px solid #fff
      display: flex
      align-items center
      justify-content center
      margin-right: 16px
      border-radius 2px
      color #fff
      font-size: 18px
      white-space nowrap
      @media screen and (max-width: 750px)
        width: 180px
        height: 46px
        margin-right: 20px
        font-size: 14px
    .btn-item:nth-child(2) a
        margin-right: 0
  .icon-w
    display: flex
    align-items center
    margin: 90px 0 30px
    @media screen and (max-width: 750px)
      margin: 30px 0 20px
    .icon
      margin-right: 50px
      @media screen and (max-width: 750px)
        margin-right: 26px
      &:last-child
        margin-right: 0
  .uls
    display: flex
    align-items center
    flex-wrap wrap
    margin-bottom: 30px
    .links-lis
      margin-bottom: 10px
      &:nth-child(1)
        a
          padding-left: 0
      &:last-child
        a
          margin-right: 0
      a
        font-size: 18px
        color rgba(255,255,255,.4)
        padding: 10px
        margin-right: 20px
        @media screen and (max-width: 750px)
          font-size: 14px
          padding: 5px
          margin-right: 0
  .copyright
    font-size: 18px
    color rgba(255,255,255,.4)
    @media screen and (max-width: 750px)
      font-size: 14px
</style>
