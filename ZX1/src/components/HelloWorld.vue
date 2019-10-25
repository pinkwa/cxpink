<template>
  <div class="page">
    <div class="header">
      <img src="../assets/img/header.jpg" alt />
    </div>
    <div class="main">
      <div class="main-clo">
        <div class="main-clo-son-first">
          <div class="main-clo-son-inside">
            <div class="main-clo-son-inside-number">
              <span ref="numberGrow" :data-time="time" :data-value="value"></span>
              <span>元</span>&nbsp;&nbsp;&nbsp;
            </div>
          </div>
        </div>
        <div class="main-seccond">
          <ul>
            <li>
              <div class="main-ul">
                <input class="left" placeholder="请输入您的房屋面积" />
                <div class="right">
                  <i class="iconfont jt">&#xe60f;</i>
                </div>
              </div>
            </li>
            <li>
              <div class="main-ul">
                <input class="left" placeholder="请输入您所在的城市" />
                <div class="right">
                  <i class="iconfont jt">&#xe624;</i>
                </div>
              </div>
            </li>

            <li>
              <div class="main-ul">
                <input class="left" placeholder="办公室 酒店 餐饮 民宿 医疗美容" />
                <div class="right">
                  <i class="iconfont jt">&#xe624;</i>
                </div>
              </div>
            </li>
            <li>
              <div class="main-ul">
                <input class="left" placeholder="输入手机号，报价结果将发到您手机上" />
                <div class="right">
                  <i class="iconfont jt">&#xe624;</i>
                </div>
              </div>
            </li>
            <div class="main-botton">立即计算</div>
          </ul>
        </div>
      </div>
    </div>
    <div class="footer">
      <div class="footer-herder">
        <p class="first">专注商业空间设计与装修</p>
        <p class="last">我们更懂公装 更专业</p>
      </div>
      <div class="fotter-main">
        <div class="fotter-main-design">
          <div class="design-left">
            <div class="left-words">
              <p class="first">设计</p>
              <p>多对一服务</p>
              <p>最大化利用空间</p>
            </div>
          </div>
          <div class="design-right">
            <img src="../assets/img/sj.jpg" alt />
          </div>
        </div>
        <div class="fotter-main-design">
          <div class="design-right">
            <img src="../assets/img/price.jpg" alt />
          </div>
          <div class="design-left">
            <div class="left-words">
              <p class="first" style="text-align: right; margin-right:15px">价格</p>
              <p>精准透明0增项</p>
            </div>
          </div>
        </div>
        <div class="fotter-main-design">
          <div class="design-left">
            <div class="left-words">
              <p class="first">工期</p>
              <p>工期短 按时交付</p>
            </div>
          </div>
          <div class="design-right">
            <img src="../assets/img/gq.jpg" alt />
          </div>
        </div>
        <div class="fotter-main-design">
          <div class="design-right">
            <img src="../assets/img/cl.jpg" alt />
          </div>
          <div class="design-left">
            <div class="left-words">
              <p class="first" style="text-align: right; margin-right:15px">材料</p>
              <p style="text-align: right; margin-right:15px">工厂直供</p>
              <p style="text-align: right; margin-right:15px">费用节约20%</p>
            </div>
          </div>
        </div>
        <div class="fotter-main-design">
          <div class="design-left">
            <div class="left-words">
              <p class="first">售后</p>
              <p>24小时管家服务</p>
            </div>
          </div>
          <div class="design-right">
            <img src="../assets/img/sh.jpg" alt />
          </div>
        </div>
      </div>
    </div>
    <div class="cooperation">
      <div class="cooperation-HD">
        <p class="top">COOPERATION CCASE</p>
        <P class="bottom">合作案例</P>
      </div>
      <div class="img">
        <div class="img-l">
          <img style="width:100%;height:100%" src="../assets/img/01.jpg" alt />
        </div>
        <div class="img-r">
          <img style="width:100%;height:100%" src="../assets/img/02.jpg" alt />
        </div>
      </div>
      <div class="img">
        <div class="img-l">
          <img style="width:100%;height:100%" src="../assets/img/03.jpg" alt />
        </div>
        <div class="img-r">
          <img style="width:100%;height:100%" src="../assets/img/04.jpg" alt />
        </div>
      </div>
      <div class="img">
        <div class="img-l">
          <img style="width:100%;height:100%" src="../assets/img/05.jpg" alt />
        </div>
        <div class="img-r">
          <img style="width:100%;height:100%" src="../assets/img/06.jpg" alt />
        </div>
      </div>
    </div>
    <div class="yc">
      <div class="name">
        <i class="iconfont">&#xe622;</i>
        <input type="text" placeholder="留下您的姓名，抢免费名额" />
      </div>
      <div class="name">
        <i class="iconfont">&#xe6a1;</i>
        <input type="text" placeholder="留下您手机号，方便联系" />
      </div>
      <div class="now">立即预约</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    time: {
      type: Number,
      default: 2
    },
    value: {
      type: Number,
      default: 720000
    }
  },
  mounted() {
    this.numberGrow(this.$refs.numberGrow);
  },
  methods: {
    numberGrow(ele) {
      let _this = this;
      let step = _this.value + 1000;
      let stop = _this.value - 10;
      let current = 0;
      let start = 0;
      let t = setInterval(function() {
        start += step;
        start -= stop;
        if (start > _this.value) {
          //  clearInterval(t)
          start = 3000;
          //  t = null
        }
        // if (current === start) {

        //      this._value=9000;
        // }
        current = start;
        ele.innerHTML = current
          .toString()
          .replace(/(\d)(?=(?:\d{3}[+]?)+$)/g, "$1,");
      }, 100);
    }
  },
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
// @import '../assets/icon/iconfont';
* {
  margin: 0;
  padding: 0;
}
.page {
  .header {
    img {
      width: 100%;
      height: 100%;
    }
  }
  .main {
    // background-image: linear-gradient(to right, #F9F9F9 , #DEDEDE);
    background: #f6f6f6;
    overflow: hidden;

    .main-clo {
      margin: 40px 10px;
      height: 100%;
      border-radius: 15px;
      background: #ffffff;
      overflow: hidden;
      -moz-box-shadow: -2px 1px 15px #141213;
      -webkit-box-shadow: -2px 1px 15px #141213;
      box-shadow: -2px 1px 15px #141213;
      .main-clo-son-first {
        margin: 18px 28px;
        background: #d8d9d1;
        height: 90px;
        border-radius: 10px;
        overflow: hidden;
        .main-clo-son-inside {
          margin: 10px;
          background: #3f4032;
          height: 70px;
          border-radius: 5px;
          overflow: hidden;
          .main-clo-son-inside-number {
            height: 50px;
            background: #d8d9d1;
            margin: 11px;
            line-height: 50px;
            // text-align: right;
            font-weight: 700;
            font-size: 35px;
            text-align: right;
          }
          p {
            display: inline;
            float: right;
          }
        }
      }
      .main-seccond {
        margin: 26px 20px;
        ul {
          list-style: none;
          li {
            height: 70px;
            line-height: 70px;
            padding: 0 34px;
            border-radius: 6px;
            background: #ebebeb;
            margin-right: 4px;
            margin-top: 18px;
            .main-ul {
              display: flex;
              justify-content: space-between;

              .left {
                // color: #ebebeb;
                background: #ebebeb;
                outline: none;
                border: none;
                font-size: 20px;
                height: 70px;
                overflow: hidden;
                white-space: nowrap;
                text-overflow: ellipsis;
              }
              // .left:focus{
              //   border:none;
              //   color: #ebebeb;
              // }
              .right {
                .jt {
                  font-size: 23px;
                  color: #828282;
                }
              }
            }
          }
          .main-botton {
            text-align: center;
            background: #fe7d15;
            color: #ffffff;
            font-size: 25px;
            height: 80px;
            line-height: 80px;
            padding: 0 34px;
            border-radius: 6px;
            margin-top: 18px;
          }
        }
      }
    }
  }
  .footer {
    margin-top: 30px;

    background: #fa9c2a;
    overflow: hidden;
    .footer-herder {
      text-align: center;
      height: 120px;
      overflow: hidden;
      p {
        color: #fffffa;

        margin: 20px;
      }
      .first {
        letter-spacing: 4px;
        font-size: 25px;
        font-weight: 700;
      }
      .last {
        font-size: 25px;
      }
    }
    .fotter-main {
      background: #ffffff;
      padding: 0 34px;
      margin: 0 20px;
      margin-bottom: 35px;
      border-radius: 20px;
      .fotter-main-design {
        height: 290px;
        display: flex;
        .design-left {
          flex: 1;
          .left-words {
            margin: 88px 0px 70px 0px;
            //  background: red;
            height: 120px;
            p {
              font-size: 26px;
              margin: 10px 0;
              color: #5a5a5a;
            }
            .first {
              font-weight: 700;
            }
          }
        }
        .design-right {
          flex: 1;
          img {
            width: 100%;
            height: 100%;
          }
        }
      }
      .fotter-main-price {
        height: 290px;
        display: flex;
        .design-left {
          flex: 1;
          .left-words {
            margin: 88px 0px 70px 0px;
            //  background: red;
            height: 120px;
            p {
              font-size: 26px;
              margin: 10px 0;
              color: #5a5a5a;
            }
            .first {
              font-weight: 700;
            }
          }
        }
      }
    }
  }
  .cooperation {
    .cooperation-HD {
      height: 170px;
      text-align: center;
      p {
        font-size: 30px;
        font-weight: 700;
        color: #333333;
      }
      .top {
        margin-top: 40px;
      }
      .bottom {
        margin: 20px 0;
      }
    }
    .img {
      display: flex;
      // height: 225px;
      margin-bottom: 30px;
      .img-l {
        margin-left: 18px;
      }
      .img-r {
        margin: 0 18px;
      }
    }
  }
  .yc {
    margin-left: 26px;
    margin-right: 20px;
    .name {
      border: 2px solid #9b9b9b;
      height: 60px;
      margin-bottom: 25px;
      border-radius: 14px;
      line-height: 60px;
      i {
        margin: 0 10px;
        font-size: 30px;
      }
      input {
        height: 76%;
        width: 83%;
        //  border: 0px solid #fff;
        border: none;
        outline: none;
      }
      input::-webkit-input-placeholder {
        color: #989898; /* placeholder颜色  */
        font-size: 23px; /* placeholder字体大小  */
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        /* placeholder位置  */
      }
    }
    .now {
      text-align: center;
      height: 75px;
      background: #fc8e1d;
      font-size: 30px;
      color: #fffef8;
      line-height: 75px;
      border-radius: 8px;
    }
  }
}
</style>
