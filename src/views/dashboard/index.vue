<template>
  <div id="home">
    <div class="header">
      <van-swipe class="my-swipe" :autoplay="3000" indicator-color="white">
        <van-swipe-item v-for="item in banner" :key="item.id">
          <a :href="item.url">
            <img :src="item.img" alt="" />
          </a>
        </van-swipe-item>
      </van-swipe>
    </div>
    <div class="content">
      <div class="detail">
        <van-row type="flex" justify="space-between">
          <van-col span="11">
            <div class="MyPatients">
              <div>
                <img src="@/assets/images/touxiang.png" alt="" />
                <span>我的患者</span>
              </div>
              <div class="con">
                <div class="title">
                  100
                </div>
                <div class="renshu">
                  我的管理人数
                </div>
                <router-link to="/">查看 <van-icon name="arrow"/></router-link>
              </div>
            </div>
          </van-col>
          <van-col span="12">
            <div class="MyDoctor">
              <div>
                <img src="@/assets/images/touxiang.png" alt="" />
                <span>我的医生</span>
              </div>
              <div class="con">
                <div class="title">
                  杨新华 <van-tag plain type="primary">妇科</van-tag>
                </div>
                <div class="renshu">
                  上海市第一妇幼保健院
                </div>
                <router-link to="/">查看 <van-icon name="arrow"/></router-link>
              </div>
            </div>
          </van-col>
        </van-row>
      </div>
      <div class="record">
        <div class="nav">
          <img src="@/assets/images/jilu.png" alt="" />
          <span class="title">
            帮患者记录
          </span>
        </div>
        <div class="log">
          <van-row type="flex" align="center" class="jiank">
            <van-col span="6">
              <div>健康日志</div>
            </van-col>
            <van-col span="8"
              ><van-progress pivot-text="" :percentage="20" stroke-width="5"
            /></van-col>
            <van-col span="6" class="nums">20次</van-col>
          </van-row>
          <van-row type="flex" align="center">
            <van-col span="6">
              <div>调查问卷</div>
            </van-col>
            <van-col span="8"
              ><van-progress pivot-text="" :percentage="10" stroke-width="5"
            /></van-col>
            <van-col span="6" class="nums">10次</van-col>
          </van-row>
        </div>
        <van-divider :style="{ borderColor: '#F5F5F5' }"> </van-divider>
        <div class="benyue">本月记录统计</div>
      </div>
      <div class="fucha">
        <div class="nav">
          <img src="@/assets/images/lingdang.png" alt="" />
          <span class="title">
            复查提醒
          </span>
        </div>
        <van-row>
          <van-col span="20">
            <div class="title">张某某术后一个月复查</div>
            <div class="riqi">2020-09-09</div>
          </van-col>
          <van-col span="4">
            <div class="date">12/20</div>
          </van-col>
        </van-row>
      </div>
      <div class="jklog">
        <div class="nav">
          <img src="@/assets/images/xiangqing.png" alt="" />
          <span class="title">
            健康日志
          </span>
        </div>
         <van-row>
          <van-col span="20">
            <div class="title">张某某术后一个月复查</div>
            <div class="riqi">2020-09-09</div>
          </van-col>
          <van-col span="4">
            <div class="date">12/20</div>
          </van-col>
        </van-row>
      </div>
      <div class="zhibo">
        <div class="nav">
          <img src="@/assets/images/zhibo.png" alt="" />
          <span class="title">
            直播通知
          </span>
        </div>
         <van-row>
          <van-col span="20">
            <div class="title">张某某术后一个月复查</div>
            <div class="riqi">2020-09-09</div>
          </van-col>
          <van-col span="4">
            <div class="date">12/20</div>
          </van-col>
        </van-row>
      </div>
    </div>
  </div>
</template>

<script>
import { home } from "@/apis/home";
export default {
  name: "home",
  data() {
    return {
      banner: [],
      dataStatistics: {},
      massage: []
    };
  },
  methods: {
    LoadHome() {
      home().then(res => {
        this.banner = res.data.banner;
        this.dataStatistics = res.data.tongji;
        this.massage = res.data.tixing;
      });
    }
  },
  mounted() {
    this.LoadHome();
  }
};
</script>

<style lang="less">
#home {
  text-align: left;
  padding-bottom: 40px;
  .header {
    // height: 192px;
    .my-swipe .van-swipe-item {
      color: #fff;
      font-size: 20px;
      height: 192px;
      line-height: 192px;
      text-align: center;
      background-color: #39a9ed;
      a {
        display: inline-block;
        width: 100%;
        height: 192px;
        img {
          width: 100%;
          height: 192px;
        }
      }
    }
  }

  .title {
    font-size: 18px;
    color: rgba(64, 64, 64, 1);
    line-height: 20px;
    padding-left: 5px;
    margin-bottom: 20px;
    font-weight: bold;
  }
  .content {
    margin: 15px;
    .detail {
      .MyPatients,
      .MyDoctor {
        padding: 15px;
        padding-left: 6px;
        border-radius: 3px;
        background-color: #fff;
        img {
          margin-bottom: 5px;
          width: 48px;
          height: 48px;
          vertical-align: middle;
        }
        .con {
          margin-left: 15px;
          .title {
            font-size: 22px;
            color: rgba(64, 64, 64, 1);
            // line-height: 20px;
            padding-left: 0px;
            margin-bottom: 9px;
            font-weight: bold;
          }
          .renshu {
            font-size: 14px;
            color: rgba(153, 153, 153, 1);
            margin-bottom: 16px;
          }
        }

        a {
          color: rgba(103, 145, 250, 1);
          font-size: 12px;
        }
      }
      .MyDoctor {
        padding-right: 10px;
        .van-tag::after {
          border-radius: 4px;
        }
        .van-tag--primary.van-tag--plain {
          vertical-align: bottom;
          border-radius: 8px;
        }
      }
    }
    .record {
      border-radius: 8px;
      margin-top: 15px;
      padding: 14px 17px;
      background-color: #fff;
      .van-progress__portion {
        background: linear-gradient(
          90deg,
          rgba(109, 177, 255, 1) 0%,
          rgba(64, 120, 244, 1) 100%
        );
      }
      .nav {
        margin-bottom: 23px;
        img {
          width: 16px;
          height: 19px;
          vertical-align: text-bottom;
        }
      }
      .log {
        .jiank {
          margin-bottom: 15px;
        }
        .nums {
          margin-left: 28px;
        }
      }
      .benyue {
        margin: 14px 0 0;
        color: #999999;
        font-size: 12px;
      }
    }
    .fucha,
    .jklog,
    .zhibo {
      padding: 15px;
      background-color: #fff;
      margin-top: 15px;
      .nav {
        margin-bottom: 23px;
        img {
          width: 20px;
          vertical-align: text-bottom;
        }
      }
      .van-row {
        .title {
          font-size: 16px;
          margin-bottom: 7px;
          padding-left: 0;
        }
        .riqi {
          font-size: 14px;
          color: rgba(153, 153, 153, 1);
        }
        .date {
          width: 40px;
          height: 40px;
          background: url("~@/assets/images/rili.png") no-repeat;
          background-size: 40px auto;
          line-height: 48px;
          text-align: center;
          color: #4589ed;
          font-size: 12px;
        }
      }
    }
  }
}
</style>
