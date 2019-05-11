<template>
  <div class="hello">
    <img src="../assets/header-bg.jpg" class="background">

    <div class="header-layout">
      <div class="header-line1">
        <p>累计净水量 647升</p>
        <p>已守护时长 75天</p>
      </div>
      <div class="vertical-layout right-pannel">
        <img v-on:click="switchPannel" class="icon-big" src="../assets/ic_tool.png">
        <img v-if="isOpenPannel" class="icon-small" src="../assets/ic_shutdown.png">
        <span v-if="isOpenPannel" class="txt">关机</span>
        <img v-if="isOpenPannel" class="icon-small" src="../assets/ic_ql.png">
        <span v-if="isOpenPannel" class="txt">强冲</span>
      </div>
      <img class="icon-big left-top" src="../assets/ic_xh.png">

      <img class="ring" src="../assets/half-ring.png">

      <div class="header-line2">
        <span class="h1">正常</span>
        <span class="h2">7453升</span>
        <span class="h3">剩余流量</span>
        <span class="h4">本次净水量1.27升</span>
      </div>

      <div class="header-line3">
        <div class="sp"></div>
        <img class="icon-bottom" src="../assets/ic_ys.png">
        <div class="vertical-layout">
          <span class="t1">原水TDS</span>
          <span class="t2">226PPM</span>
        </div>
        <div class="grow"></div>
        <img class="icon-bottom" src="../assets/ic_ys.png">
        <div class="vertical-layout">
          <span class="t1">纯水TDS</span>
          <span class="t2">6PPM</span>
        </div>
        <div class="sp"></div>
      </div>
      <div class="menu-layout">
        <div class="vertical-layout item-menu">
          <img class="icon-menu" src="../assets/ic_sb.png">
          <span class="icon-txt">我的设备</span>
        </div>
        <div class="vertical-layout item-menu">
          <img class="icon-menu" src="../assets/ic_cz.png">
          <span class="icon-txt">我要充值</span>
        </div>
        <div class="vertical-layout item-menu">
          <img class="icon-menu" src="../assets/ic_lx.png">
          <span class="icon-txt">我的滤芯</span>
        </div>
        <div class="vertical-layout item-menu">
          <img class="icon-menu" src="../assets/ic_bx.png">
          <span class="icon-txt">我要保修</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      isOpenPannel: false
    };
  },
  methods: {
    switchPannel() {
      this.isOpenPannel = !this.isOpenPannel;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
  display: flex;
  flex-direction: column;
}
.background {
  width: 100%;
  height: 20rem;
  position: absolute;
  top: 0;
}
.ring {
  width: 11rem;
  position: absolute;
  transform: translate(-50%, 0);
  left: 50%;
  top: 3.8rem;
}
.header-layout {
  z-index: 50;
  width: 100%;
  position: absolute;
  top: 0;
}
.header-line1 {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(60, 60, 60, 0.24);
  height: 2.69rem;
}

.header-line1 p {
  font-size: 1rem;
  font-family: PingFangSC-Medium;
  color: rgba(255, 255, 255, 1);
  line-height: 1.67rem;
  padding: 0 1rem 0 1rem;
}
.icon-big {
  width: 1.38rem;
}

.header-layout .left-top {
  padding: 0.8rem;
}

.right-pannel {
  align-items: center;
  padding: 0.35rem;
  margin: 0.5rem;
  right: 0;
  position: absolute;
  background: rgba(25, 25, 25, 0.2);
  border-radius: 0.5rem;
  .txt {
    color: white;
    font-size: 0.63rem;
    font-family: PingFangSC-Medium;
  }
  .icon-small {
    width: 1rem;
    padding: 0.7rem 0 0.3rem 0;
  }
}
.vertical-layout {
  display: flex;
  flex-direction: column;
}
.grow {
  flex-grow: 1;
}

.header-line2 {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  span {
    color: white;
  }
  .h1 {
    color: greenyellow;
    font-weight: 600;
    padding: 0.3rem 0 0.9rem 0;
  }
  .h2 {
    font-size: 1.6rem;
    font-weight: 800;
  }
  .h3 {
    font-size: 0.94rem;
    font-weight: 500;
  }
  .h4 {
    font-size: 0.81rem;
    font-family: PingFangSC-Light;
    font-weight: 300;
    padding-top: 1rem;
  }
}
.header-line3 {
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 2.4rem;
  .icon-bottom {
    width: 1.31rem;
    height: 1.75rem;
    padding: 0 0.5rem 0 0;
  }
  .sp {
    width: 0.6rem;
  }
  .t1 {
    font-size: 0.75rem;
    font-family: PingFangSC-Regular;
    font-weight: 400;
    color: rgba(255, 255, 255, 1);
    line-height: 1.06rem;
  }
  .t2 {
    font-size: 1rem;
    font-family: PingFangSC-Medium;
    font-weight: 500;
    color: rgba(255, 255, 255, 1);
    line-height: 1.38rem;
  }
}
.menu-layout {
  width: 100%;
  margin-top: 1rem;
  height: calc(100vh - 20rem);
  display: grid;
  grid-template-columns: auto auto;
  grid-template-rows: auto auto;

  .item-menu {
    align-items: center;
    justify-content: center;
  }
  .icon-menu {
    width: 2.4rem;
    height: 2.4rem;
    padding-bottom: 1rem;
  }
  .icon-txt {
    font-size: 1.13rem;
    font-family: PingFangSC-Medium;
    font-weight: 500;
    color: rgba(72, 72, 72, 1);
    line-height: 1.56rem;
  }
}
</style>
