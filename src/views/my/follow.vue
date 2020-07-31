<template>
  <div id="follow">
    <van-nav-bar
      title="我的关注"
      left-arrow
      @click-left="onClickLeft"
      class="nav"
    >
    </van-nav-bar>
    <van-tabs @click="onClick">
      <van-tab title="全部">
        <van-pull-refresh
          v-model="isLoading"
          success-text="刷新成功"
          @refresh="onRefresh"
        >
          <div class="content">
            <van-row type="flex" align="center">
              <van-col span="4" class="avatar"
                ><img :src="require('@/assets/images/avatar.png')" alt=""
              /></van-col>
              <van-col span="12">
                <div>董莹莹</div>
                <div>这里是医院名称</div>
              </van-col>
              <van-col span="8">
                <div class="play">
                  <img src="@/assets/images/play.png" alt="" /><span
                    >查看回放</span
                  >
                </div>
              </van-col>
            </van-row>
          </div>
        </van-pull-refresh>
      </van-tab>
      <van-tab title="患者"
        ><van-pull-refresh
          v-model="isLoading"
          success-text="刷新成功"
          @refresh="onRefresh"
        >
          <div class="content">
            <van-row type="flex" align="center">
              <van-col span="4" class="avatar"
                ><img :src="require('@/assets/images/avatar.png')" alt=""
              /></van-col>
              <van-col span="12">
                <div>董莹莹</div>
                <div>这里是医院名称</div>
              </van-col>
              <van-col span="8">
                <div class="play">
                  <img src="@/assets/images/play.png" alt="" /><span
                    >查看回放</span
                  >
                </div>
              </van-col>
            </van-row>
          </div>
        </van-pull-refresh></van-tab
      >
      <van-tab title="主管医生"
        ><van-pull-refresh
          v-model="isLoading"
          success-text="刷新成功"
          @refresh="onRefresh"
        >
          <div class="content">
            <van-row type="flex" align="center">
              <van-col span="4" class="avatar"
                ><img :src="require('@/assets/images/avatar.png')" alt=""
              /></van-col>
              <van-col span="12">
                <div>董莹莹</div>
                <div>这里是医院名称</div>
              </van-col>
              <van-col span="8">
                <div class="play">
                  <img src="@/assets/images/play.png" alt="" /><span
                    >查看回放</span
                  >
                </div>
              </van-col>
            </van-row>
          </div>
        </van-pull-refresh></van-tab
      >
    </van-tabs>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // active:0
      isLoading: false
    };
  },
  methods: {
    onClickLeft() {
      this.$router.go(-1); //返回上一层
    },
    onClick(name, title) {
      this.$toast(name);
    },
    onRefresh() {
      setTimeout(() => {
        this.isLoading = false;
      }, 1000);
    }
  },
  mounted() {}
};
</script>

<style lang="less">
#follow {
  text-align: left;
  .van-nav-bar {
    background: rgba(241, 241, 241, 1);
  }
  .van-nav-bar__left {
    .van-icon {
      color: #404040;
    }
  }
  .content {
    padding: 0 20px;
    background-color: #fff;
    .van-row {
      padding: 20px 0;
      border-bottom: 1px solid rgba(245, 245, 245, 1);
      &:last-child {
        border-bottom: none;
      }
    }
    .play {
      text-align: right;
      font-size: 12px;
      color: rgba(69, 137, 237, 1);
      img {
        width: 20px;
        vertical-align: middle;
        margin-right: 6px;
      }
      span {
        vertical-align: middle;
      }
    }
  }
}
</style>
