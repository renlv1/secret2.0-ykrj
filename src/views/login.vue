<template>
  <div @keyup.enter="loginTo">
    <div class="login-w">
      <div class="left-w">
        <h3 class="left-title m-title">{{$t('header.text19')}}</h3>
        <div class="p-a" v-for="(item, index) in $t('newsArr')" :key="index">
          <div class="title">{{item.title}}</div>
<!--          <div v-html="item.content" class="content" v-if="index === 0"></div>-->
        </div>
      </div>
      <div class="right-w">
        <h3 class="right-title m-title">{{$t('header.text20')}}</h3>
        <p class="p-a">{{$t('header.text21')}}</p>
        <div class="input-a"><input type="text" :placeholder="$t('header.text22')" v-model.trim="userName"></div>
        <div class="input-a"><input type="password" :placeholder="$t('header.text23')" v-model.trim="userPwd"></div>
        <div class="err-c">{{errMsg}}</div>
        <div class="btn" @click="loginTo" :class="{'loadingbtn': loadingShow}">
          <img src="../assets/img/common/loading.gif" alt="" v-show="loadingShow">
          <span>{{$t('header.text20')}}</span>
        </div>
        <div class="f-b pc-b">
          <a href="https://trade.secretworth.com/#/register" class="a-c" target="_blank">{{$t('header.text26')}}</a>
          <a href="https://trade.secretworth.com/#/getBackPwd" class="a-c" target="_blank">{{$t('header.text25')}}</a>
        </div>
        <div class="f-b m-b">
          <a href="https://mtrade.secretworth.com/#/register" class="a-c" target="_blank">{{$t('header.text26')}}</a>
          <a href="https://mtrade.secretworth.com/#/forget" class="a-c" target="_blank">{{$t('header.text25')}}</a>
        </div>
        <a href="https://trade.secretworth.com/#/home/holdings"  target="_blank" ref="pcBtn"></a>
        <a href="https://mtrade.secretworth.com/#/hold" target="_blank" ref="mBtn"></a>
      </div>
    </div>
  </div>

</template>

<script type="text/ecmascript-6">
	export default {
		data() {
			return {
        loadingShow: false,
        userName: '',
        userPwd: '',
        errMsg: ''
      }
		},
    created () {
    },
    methods: {
      loginTo () {
        this.errMsg = ''
        if (this.userName === '') {
          this.errMsg = this.$t('header.text22')
          return
        }
        if (this.userPwd === '') {
          this.errMsg = this.$t('header.text23')
          return
        }
        this.loadingShow = true
        if (this.userName.trim() !== '' && this.userPwd.trim() !== '') {
          this.$fetch.post('/user/userlogin', {
            username: this.userName,
            password: this.userPwd
          }).then((res) => {
            this.loadingShow = false
            if (res.success) {
              if (window.innerWidth > 1200) {
                this.$refs.pcBtn.click()
              }else {
                window.location.href = 'https://mtrade.secretworth.com/#/hold'
                // this.$refs.mBtn.click()
              }
            } else {
              this.errMsg = res.msg
            }
          }).catch(() => {
            this.loadingShow = false
          })
        }
      }
    }
	}
</script>

<style scoped lang="stylus">
.f-b
  margin-top: 20px
  display: flex
  align-items center
  justify-content space-between
  @media screen and (max-width: 768px)
    font-size 16px
  .a-c
    padding: 10px 0
.pc-b
  @media screen and (max-width: 1200px)
    display: none
  @media screen and (min-width: 1200px)
    display: flex
    font-size: 16px
.m-b
  @media screen and (max-width: 1200px)
    display: flex
  @media screen and (min-width: 1200px)
    display: none
.login-w
  display: flex
  width: 1300px
  margin: 30px auto 0
  box-shadow 0 0 5px #eee
  padding: 80px
  @media screen and (max-width: 1300px)
    width: 100%
    padding: 20px
    box-shadow none
  .m-title
    font-size: 38px
    color #2d3436
    @media screen and (max-width: 1200px)
      font-size: 20px
  .p-a
    font-size: 20px
    color #636e72
    margin-bottom: 20px
    .title
      font-size: 20px
      color  #636e72
      margin-bottom: 20px
    .content
      font-size: 16px
      color #636e72
      overflow: hidden;
      display: -webkit-box;
      -webkit-line-clamp: 3;
      -webkit-box-orient: vertical;
      >>> p
        font-size: 0
      >>> span
        color #636e72 !important
  .left-w
    width: 500px
    padding-right: 100px
    @media screen and (min-width: 1200px)
      display: block
    @media screen and (max-width: 1200px)
      display: none
    .left-title
      margin-bottom: 30px
  .right-w
    flex 1
    padding-left: 100px
    border-left: 1px solid #dfe6e9
    @media screen and (max-width: 1200px)
      padding: 0 10px
      border-left none
    .p-a
      margin: 30px 0
    .err-c
      color #ff7675
      font-size: 14px
      margin-bottom: 10px
    .input-a
      width:  100%
      @media screen and (max-width: 1200px)
        width: 100%
      input
        width: 100%
        height: 68px
        padding-left: 20px
        border-radius 4px
        font-size: 16px
        border: 1px solid #dfe6e9
        margin-bottom: 30px
        @media screen and (max-width: 1200px)
          height: 42px
          margin-bottom: 10px
          font-size: 14px
    .btn
      width: 100%
      height: 68px
      cursor pointer
      display: flex
      align-items center
      justify-content center
      background-color: #ff7675
      border-radius 4px
      font-size: 16px
      border: 1px solid #dfe6e9
      color #fff
      &.loadingbtn
        pointer-events none
      @media screen and (max-width: 1200px)
        width: 100%
        height: 42px
      img
        width: 30px
        display: block
        margin-right: 10px
</style>
