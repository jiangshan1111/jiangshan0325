<template>
  <div class="content-box" id="user-center" style=" margin-top:75px;min-height: 600px; height: auto;">
    <usersLeft />
    <router-view :key="this.$route.path" />
  </div>
</template>

<script>
export default {
  components: {
    usersLeft: () => import('@/components/users-left.vue')
  },
  data() {
    return {
      activeIndexa: 1,
      activeIndexb: 0,
      courses: [{}, {}, {}, {}, {}, {}, {}, {}, {}, {}]
    }
  },
  created() {},
  methods: {
    activeA(num) {
      this.activeIndexa = num
    },
    goNext(router) {
      this.$router
        .push({
          path: router
        })
        .catch((err) => {
          console.log(err)
        })
    },
    activeB(num) {
      this.activeIndexb = num
    }
  }
}
</script>
<style lang="scss">
#user-center {
  width: 1220px;
  height: 100%;
  margin: 20px auto 30px;
  overflow: hidden;
  padding: 8px;
  position: relative;
  .content-left {
    width: 205px;
    height: 100%;
    float: left;
    background-color: #fff;
    padding-bottom: 60px;
    box-shadow: 0px 0px 8px rgb(210, 210, 210);
  }
  .content-right {
    width: 970px;
    height: auto;
    float: right;
    background-color: #fff;
    box-shadow: 0px 0px 8px rgb(210, 210, 210);
  }
  .headpic {
    width: 205px;
    height: 196px;
    border-bottom: 1px solid #e2e2e4;
  }
  .write div {
    margin-left: 5px;
    color: #c8c5bf;
  }
  .content-left .headpic .pic {
    box-sizing: content-box;
    width: 55px;
    height: 53px;
    margin: 15px auto 0;
    background-color: #aaaaaa;
    border-radius: 100px;
    background-repeat: no-repeat;
    padding: 20px 19px;
    position: relative;
    cursor: pointer;
    background-size: contain;
  }
  .setup {
    font-size: 14px;
    color: #fff;
    position: absolute;
    top: 69px;
    left: 32px;
    display: none;
    z-index: 5;
  }
  .maskpic {
    position: absolute;
    top: 67px;
    left: 4px;
    z-index: 3;
    display: none;
  }
  .content-left .headpic .headtit {
    margin: 12px 0 0 0;
    font-size: 14px;
    color: #474746;
    text-align: center;
  }
  .headlabel {
    margin: 14px 18px 0 19px;
    line-height: 20px;
    font-size: 12px;
    color: #777570;
  }
  .headlabel2 {
    margin: 16px 14px 0 19px;
    line-height: 22px;
    font-size: 12px;
    color: #777570;
  }
  .static {
    /*display: none;*/
  }
  .write {
    display: none;
    position: relative;
  }
  .write textarea {
    width: 154px;
    height: 40px;
    resize: none;
  }
  @-moz-document url-prefix() {
    .write textarea {
      height: 48px;
    }
  }
  .headlabel .iconfont {
    margin-left: 10px;
  }
  .content-left li {
    padding: 5px 0 4px 50px;
    width: 170px;
    height: 37px;
    line-height: 28px;
    cursor: pointer;
    border-left: 3px solid transparent;
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
  }
  .content-left li:hover span {
    color: #00b2ea;
  }
  .font-num {
    position: absolute;
    right: 5px;
    top: 32px;
    font-size: 8px;
    color: #c8c5bf;
  }
  @-moz-document url-prefix() {
    .font-num {
      top: 40px;
    }
  }
  .content-left li.label-active {
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
  }
  .content-left li.label-active span {
    color: #00b2ea;
  }
  .content-left li span img {
    position: absolute;
    right: -8px;
    top: 0px;
  }
  .content-left li span {
    color: #777570;
    font-size: 14px;
    position: relative;
  }
  .content-left li span.iconfont {
    font-size: 16px;
    margin-right: 12px;
  }
  .content-left li span.changeSmall {
    font-size: 12px;
    margin-right: 15px;
    left: 2px;
  }
  .content-left .dashed {
    margin: 0 34px 0 20px;
    border-top: 1px dashed #e2e2e4;
  }
  .right-box {
    margin-left: 40px;
    width: 880px;
    height: auto;
  }
  .mynote-title {
    margin-top: 10px;
    line-height: 35px;
    font-size: 18px;
    color: #474746;
    border-bottom: 1px solid #e2e2e4;
  }
  .right-nav {
    height: 35px;
    width: 100%;
    background-color: #f2f3f4;
    margin-top: 5px;
    margin-bottom: 10px;
    clear: both;
    position: relative;
  }
  .mark {
    width: 100%;
    border: 1px solid #fff;
  }
  .mark .iconfont {
    display: inline-block;
    width: 23px;
  }
  .mark-active {
    height: 23px;
    line-height: 23px;
    text-align: center;
    border: 1px solid #00baee;
    background-color: #fff;
    padding-left: 8px;
    color: #00baee;
    border-radius: 3px;
    margin-right: 15px;
  }
  .mark-active a {
    text-decoration: none;
    color: #00baee;
  }
  .mark-active .iconfont {
    border-left: 1px solid #00baee;
  }
  .mark-failed {
    height: 23px;
    line-height: 23px;
    text-align: center;
    border: 1px solid #e2e2e4;
    background-color: #f3f3f3;
    padding-left: 8px;
    color: #777570;
    border-radius: 3px;
    margin-right: 15px;
  }
  .mark-failed a {
    text-decoration: none;
    color: #777570;
  }
  .mark-failed .iconfont {
    border-left: 1px solid #e2e2e4;
  }
  .all-course {
    height: 34px;
    width: 43px;
    line-height: 34px;
    text-align: center;
    color: #82807b;
    font-size: 14px;
    cursor: pointer;
  }
  .note-bottom a.chapterlink:hover {
    color: #00b2ea;
  }
  .dropdown {
    width: 20px;
    height: 34px;
    line-height: 34px;
    text-align: center;
    cursor: pointer;
  }
  .pop {
    position: absolute;
    top: 32px;
    left: 5px;
    background-color: #fafafa;
    border: 1px solid #ddd;
    display: none;
  }
  .pop li {
    height: 24px;
    width: auto;
    line-height: 24px;
    padding: 0 10px;
    color: #9a9691;
    border-bottom: 1px solid #ddd;
    cursor: pointer;
  }
  .pop li:last-child {
    border-bottom: 0px;
  }
  .pop li:hover {
    background-color: #f2f3f4;
  }
  .search {
    width: 177px;
    height: 23px;
    margin-top: 4px;
    margin-right: 20px;
    background-color: #fff;
    border: 1px solid #dfddd8;
    position: relative;
  }
  .search input {
    width: 136px;
    height: 11px;
    border: 0px;
    color: #787878;
    position: relative;
    top: -3px;
    left: 0;
  }
  .glass {
    height: 22px;
    line-height: 22px;
    cursor: pointer;
  }
  .mynotes {
    width: 100%;
    height: auto;
    /*background-color: #f3f3f3;*/
    overflow: hidden;
    margin-top: 10px;
  }
  .mynotes em {
    color: #e60012;
  }
  .right-box .mynote-active {
    width: 100%;
    height: auto;
    background-color: #f3f3f3;
    overflow: hidden;
  }
  .line {
    width: 100%;
    margin: 10px 0;
    border-top: 1px solid #e2e2e4;
  }
  a.player-time {
    display: inline-block;
    width: auto;
    height: 22px;
    border: 1px solid #aea8a3;
    border-radius: 4px;
    margin: 8px 0 0 10px;
    cursor: pointer;
    color: #aea8a3;
    text-decoration: none;
  }
  /*a.player-time:hover{*/
  /*color: #00b2ea;*/
  /*border: 1px solid #00b2ea;*/
  /*}*/
  .player {
    width: 22px;
    height: 22px;
    line-height: 22px;
    text-align: center;
    float: left;
    border-right: 1px solid #aea8a3;
  }
  /* .time {
    width: auto;
    height: 220px;
    line-height: 22px;
    text-align: center;
    float: left;
    padding: 0 5px;
  } */
  .note-content {
    margin: 8px 30px 0 10px;
    font-size: 12px;
    color: #777570;
    line-height: 22px;
  }
  .note-bottom {
    margin: 22px 20px 10px 10px;
    color: #c8c5bf;
    font-size: 12px;
    overflow: hidden;
    height: 22px;
    line-height: 22px;
  }
  .noteday {
    margin-right: 10px;
  }
  .moment {
    margin-right: 20px;
  }
  .note-bottom a {
    color: #c8c5bf;
    font-size: 12px;
    text-decoration: none;
  }
  .note-bottom .edit {
    font-size: 12px;
    color: #00baee;
    margin-right: 25px;
  }
  .note-bottom .delete {
    color: #8c8984;
    font-size: 12px;
    margin-right: 20px;
  }
  .note-bottom .save {
    font-size: 12px;
    color: #00baee;
    margin-right: 25px;
  }
  .note-bottom .cancel {
    color: #8c8984;
    font-size: 12px;
    margin-right: 20px;
  }
  .edit .iconfont {
    margin-right: 4px;
    font-size: 16px;
  }
  .delete .iconfont {
    margin-right: 4px;
    font-size: 16px;
  }
  .mynotes .active-text {
    width: 802px;
  }
  .mynote-active .cancel,
  .mynote-active .save {
    width: 37px;
    height: 20px;
    border-radius: 3px;
    line-height: 20px;
    text-align: center;
  }
  .mynote-active .save {
    border: 1px solid #00baee;
    color: #00baee;
  }
  .mynote-active .cancel {
    border: 1px solid #aea8a3;
    color: #777570;
  }
  .right-box .page-box {
    height: 25px;
    line-height: 25px;
    vertical-align: bottom;
    margin-top: 70px;
    margin-bottom: 25px;
  }
  .page-box .page-no,
  .page-box a {
    border: 1px solid #cbc7c2;
    border-radius: 3px;
    color: #9a9691;
    display: inline-block;
  }
  .page-box .page-no {
    margin: 4px 25px 0 270px;
    width: 50px;
    height: 20px;
    line-height: 20px;
    text-align: center;
  }
  .page-box a {
    margin-right: 10px;
    text-align: center;
    text-decoration: none;
  }
  .page-box .pagepn {
    width: 70px;
    height: 24px;
  }
  .page-box .num {
    width: 23px;
    height: 21px;
    line-height: 21px;
    margin-top: 3px;
    text-align: center;
  }
  a.page-active {
    background-color: #00b2ea;
    color: #fff;
  }
  .page-box .omit {
    margin-right: 8px;
    margin-top: 3px;
  }
  .prompt-box {
    width: 100%;
    height: 100%;
    position: fixed;
    z-index: 100;
    background: rgba(255, 255, 255, 0.2);
    top: 0;
    left: 0;
    display: none;
  }
  .prompt {
    width: 400px;
    height: 230px;
    position: fixed;
    top: 30%;
    left: 43%;
    background-color: #fff;
    border-radius: 4px;
    box-shadow: 1px 1px 40px 1px #dddee1;
  }
  .prompt-text {
    margin-top: 60px;
    width: 100%;
    height: 23px;
    line-height: 23px;
    text-align: center;
    color: #474746;
    font-size: 14px;
  }
  .prompt-btn {
    margin: 46px 96px 0 96px;
    width: 216px;
  }
  .prompt-btn a {
    width: 97px;
    height: 33px;
    border-radius: 3px;
    display: inline-block;
    font-size: 14px;
    line-height: 33px;
    text-align: center;
    text-decoration: none;
  }
  .prompt a.prompt-yes {
    background-color: #00acd9;
    color: #fff;
    margin-right: 16px;
  }
  .prompt a.prompt-cancel {
    color: #46474a;
    border: 1px solid #d8d5d0;
  }
  .bigpic-box {
    width: 100%;
    /* height: 547px; */
  }
  .bigpic {
    width: 100%;
    height: 260px;
    background-repeat: no-repeat;
    background-position: 344px 108px;
  }
  .no-note {
    text-align: center;
    margin: 36px 0 0 0;
    font-size: 14px;
    color: #9a9691;
  }
  .bigpic-box-sec {
    width: 100%;
    height: 498px;
  }
  .nofind-note {
    text-align: center;
    margin: 36px 0 0 0;
    font-size: 14px;
    color: #9a9691;
  }
  .nofind-note span {
    color: #00baee;
  }
  .coures-box {
    width: 258px;
    height: 231px;
    margin: 20px 48px 0 0;
    border: 1px solid #e7e5e2;
    position: relative;
  }
  .coures-box .cancel-btn {
    left: 0;
  }
  .pic-box {
    height: 142px;
    width: 100%;
    overflow: hidden;
  }
  .coures-title {
    margin: 5px 0 0 10px;
    font-size: 14px;
    color: #474747;
  }
  .state-btn {
    /*width: 40px;*/
    height: 20px;
    padding: 0 8px;
    border: 1px solid #d9d9d9;
    border-radius: 3px;
    margin: 5px 0 0 8px;
    color: #bbbbbb;
    line-height: 20px;
    text-align: center;
    float: left;
    cursor: pointer;
  }
  .coures-bottom {
    margin: 10px 10px 0 10px;
    width: 238px;
    height: 22px;
  }
  .coures-font {
    font-size: 12px;
    color: #bbbbbb;
    margin-top: 3px;
  }
  .coures-bottom .iconfont {
    font-size: 14px;
    color: #bbbbbb;
    margin-right: 3px;
    margin-top: 4px;
    vertical-align: middle;
  }
  .coures-bottom span {
    display: inline-block;
    vertical-align: middle;
  }
  .coures-page-box {
    height: 25px;
    line-height: 25px;
    vertical-align: bottom;
    margin-top: 35px;
    margin-bottom: 25px;
  }
  .coures-page-box .page-no,
  .coures-page-box a {
    border: 1px solid #cbc7c2;
    border-radius: 3px;
    color: #9a9691;
    display: inline-block;
  }
  .coures-page-box .page-no {
    margin: 4px 25px 0 270px;
    width: 50px;
    height: 20px;
    line-height: 20px;
    text-align: center;
  }
  .coures-page-box a {
    margin-right: 10px;
    text-align: center;
    text-decoration: none;
  }
  .coures-page-box .pagepn {
    width: 70px;
    height: 24px;
  }
  .coures-page-box .num {
    width: 23px;
    height: 21px;
    line-height: 21px;
    margin-top: 3px;
    text-align: center;
  }
  .coures-page-box .omit {
    margin-right: 8px;
    margin-top: 3px;
  }
  .coures-page-box a.page-active {
    background-color: #00b2ea;
    color: #fff;
    border: 0px;
    width: 25px;
    height: 23px;
  }
  .right-box li .coures-box:hover {
    box-shadow: 0 0 6px #a3e6fc;
    transition: 0.4s;
    margin-top: 17px;
    margin-bottom: 3px;
  }
  .right-box li .coures-box:hover a {
    color: #00b2ea;
    text-decoration: none;
  }
  .no-coures {
    text-align: center;
    margin: 36px 0 0 0;
    font-size: 14px;
    color: #9a9691;
  }
  .bigpic-box .no-coures a {
    color: #00b2ea;
    cursor: pointer;
    text-decoration: none;
  }
  .drop-box .classify-active {
    color: #00b7ee;
  }
  .order-state {
    height: 34px;
    width: auto;
    line-height: 34px;
    text-align: center;
    color: #787878;
    font-size: 14px;
    margin-left: 20px;
    cursor: pointer;
  }
  .order-right-nav {
    height: 35px;
    width: 100%;
    background-color: #f2f3f4;
    margin-top: 5px;
    clear: both;
    position: relative;
  }
  .order-form {
    width: 100%;
    height: 178px;
    border-bottom: 1px solid #e2e2e4;
  }
  .order-form .order-name {
    width: 100%;
    height: 35px;
    line-height: 35px;
    padding-top: 10px;
    padding-left: 2px;
    font-size: 14px;
    color: #474747;
  }
  .order-form .order-info {
    width: 100%;
    height: 133px;
  }
  .order-form .d1 {
    width: 232px;
    height: auto;
    padding-top: 12px;
  }
  .order-form .d2 {
    width: 292px;
    height: auto;
    padding-top: 12px;
  }
  .order-form .d3 {
    width: 235px;
    height: auto;
    padding-top: 12px;
  }
  .order-form .d4 {
    width: 100px;
    height: auto;
    padding-top: 12px;
  }
  .order-form .order-font {
    height: 40px;
    width: auto;
    padding-left: 3px;
    font-size: 12px;
    color: #777570;
  }
  .order-form .order-btn-box {
    margin-top: 65px;
  }
  .order-form .order-btn-box a.not-pay {
    display: block;
    width: 98px;
    height: 30px;
    line-height: 30px;
    text-align: center;
    font-size: 14px;
    color: #fff;
    background-color: #33cccc;
    border-radius: 3px;
    text-decoration: none;
  }
  .order-form .order-font .failure {
    color: #ff3333;
  }
  .order-form .order-btn-box a.fail-pay {
    display: block;
    width: 98px;
    height: 30px;
    line-height: 30px;
    text-align: center;
    font-size: 14px;
    color: #fff;
    background-color: #fd5555;
    border-radius: 3px;
    text-decoration: none;
  }
  .order-form .order-btn-box a.succeed-pay {
    display: block;
    width: 98px;
    height: 30px;
    line-height: 30px;
    text-align: center;
    font-size: 14px;
    color: #fff;
    background-color: #00ccff;
    border-radius: 3px;
    text-decoration: none;
  }
  .right-box div.order-form:last-child {
    border-bottom: 0;
  }
  .order-bigpic-box {
    width: 100%;
    height: 507px;
  }
  .order-bigpic-box .no-coures a {
    color: #00b2ea;
    cursor: pointer;
    text-decoration: none;
  }
  .transline {
    width: 100%;
    border: 1px solid #fff;
    margin-top: 10px;
  }
  .free-course {
    font-size: 14px;
    color: #1eb8ec;
  }
  .course-price {
    font-size: 14px;
    color: #fe5151;
  }
  .cancel-btn {
    position: absolute;
    left: 0px;
    top: 10px;
    width: 65px;
    height: 23px;
    background: rgba(0, 0, 0, 0.5);
    color: #fff;
    font-size: 12px;
    line-height: 23px;
    text-align: center;
    cursor: pointer;
    display: none;
  }
  .bank-box .question-item {
    width: 100%;
    height: auto;
    overflow: hidden;
    border-bottom: 1px solid #dfe1e6;
  }
  .bank-box .question-item:last-child {
    border-bottom: 0px;
  }
  .bank-box .question-item .quest-title {
    height: 50px;
    width: 100%;
    line-height: 50px;
    font-size: 14px;
    color: #474747;
  }
  .bank-box .question-item .quest-title span {
    font-size: 12px;
    color: #808080;
    margin-left: 10px;
  }
  .secondtit {
    width: 830px;
    height: auto;
    color: #999999;
    font-size: 12px;
    line-height: 20px;
  }
  .course-ball {
    width: 114px;
    height: 114px;
    margin: 25px 56px 20px 0;
    line-height: 38px;
    text-align: center;
    border: 2px solid #00b7ee;
    border-radius: 100px;
    cursor: pointer;
    -webkit-box-sizing: initial;
    box-sizing: initial;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .question-item div.course-ball:hover .course-name {
    color: #3facde;
  }
  .course-ball .course-name {
    color: #474747;
    font-size: 12px;
    display: inline-block;
    width: 70px;
    height: 40px;
    line-height: 20px;
  }
  .mynote-title {
    position: relative;
  }
  .tab {
    position: absolute;
    right: 0;
    bottom: 3px;
  }
  .tab a {
    display: inline-block;
    text-align: center;
    color: #616161;
    /*width: 58px;*/
    height: 28px;
    line-height: 26px;
    background: #f3f3f3;
    border: 1px solid #dcdcdc;
    border-radius: 3px;
    margin-left: 8px;
    padding: 0 16px;
    font-size: 12px;
  }
  .tab a.btn-myclass {
    display: inline-block;
    width: 70px;
  }
  .tab a.active {
    color: #fff;
    border-color: #00b7ee;
    background: #00b7ee;
  }
  .tab a:hover {
    text-decoration: none;
    color: #616161;
  }
  .tab a.active:hover {
    color: #fff;
  }
  i,
  em {
    font-style: normal;
  }
  .content-wrap {
    width: 930px;
  }
  .cancel-btn {
    z-index: 100;
    left: 10px;
  }
  .content-wrap .content > li {
    width: 270px;
    margin: 20px 33px 20px 0;
    border-radius: 3px;
    position: relative;
    background: #fff;
    z-index: 1;
    float: left;
    cursor: default;
  }
  .class-bg-layer {
    -webkit-transition: all 0.3s ease;
    -moz-transition: all 0.3s ease;
    -o-transition: all 0.3s ease;
    transition: all 0.3s ease;
    position: absolute;
    top: 5px;
    left: 5px;
    right: 5px;
    height: 100%;
    background-color: #fff;
    -webkit-border-radius: 2px;
    -moz-border-radius: 2px;
    border-radius: 2px;
    -webkit-box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.1);
    -moz-box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.1);
    box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.1);
    z-index: -1;
  }
  .class-item-bg {
    width: 270px;
    height: 260px;
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    background-color: #fff;
    padding: 10px;
    -webkit-border-radius: 2px;
    -moz-border-radius: 2px;
    border-radius: 2px;
    -webkit-box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
    -moz-box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
    box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.3s ease;
    -moz-transition: all 0.3s ease;
    -o-transition: all 0.3s ease;
    transition: all 0.3s ease;
  }
  .content-wrap .content > li:hover .cancel-btn {
    display: block;
  }
  .content-wrap .content > li:hover .class-bg-layer {
    transform: translateY(-6px);
    -webkit-transform: translateY(-6px);
    -moz-transform: translateY(-6px);
    box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.1), 0 2px 4px 0 rgba(0, 0, 0, 0.1);
    -webkit-box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.1), 0 2px 4px 0 rgba(0, 0, 0, 0.1);
    -moz-box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.1), 0 2px 4px 0 rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.4s 0.05s ease;
    -moz-transition: all 0.4s 0.05s ease;
    transition: all 0.4s 0.05s ease;
  }
  .content-wrap .content > li:hover .class-item-bg {
    transform: translateY(-8px);
    -webkit-transform: translateY(-8px);
    -moz-transform: translateY(-8px);
    box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.1), 0 2px 6px 0 rgba(0, 0, 0, 0.1);
    -webkit-box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.1), 0 2px 6px 0 rgba(0, 0, 0, 0.1);
    -moz-box-shadow: 0 4px 6px 0 rgba(0, 0, 0, 0.1), 0 2px 6px 0 rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.3s ease;
    -moz-transition: all 0.3s ease;
    -o-transition: all 0.3s ease;
    transition: all 0.3s ease;
  }
  .content-wrap li .class-item-bg > a {
    display: block;
    width: 250px;
    height: 134px;
  }
  .content-wrap li img {
    width: 100%;
    height: 134px;
  }
  .content-wrap li h1 a {
    font-size: 14px;
    line-height: 30px;
    color: #474747;
  }
  .content-wrap li h1 a:hover {
    text-decoration: none;
  }
  .content-wrap li p {
    font-size: 12px;
    color: #bbb;
    height: 14px;
  }
  .info-wrap {
    margin: 10px 0 6px;
  }
  .left-info li {
    float: left;
    font-size: 12px;
    color: #949494;
    padding-left: 10px;
  }
  .left-info li:first-child {
    padding-left: 0;
  }
  .left-info li i {
    margin: 0 10px;
  }
  .left-info li em.border {
    position: relative;
    top: -1px;
    border: 0;
  }
  .people-num {
    color: #bbb;
    font-size: 12px;
  }
  .price {
    font-size: 14px;
    color: #fe5151;
  }
  .price.free {
    color: #00b7ee;
  }
  .pages {
    margin: 35px 0 25px;
  }
  .content-right .box {
    margin-left: 40px;
    height: auto;
    margin-right: 40px;
  }
}
</style>
