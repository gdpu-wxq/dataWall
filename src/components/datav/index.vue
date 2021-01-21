<template>
  <div id="data-view">
    <dv-full-screen-container>
      <div class="main-header">
        <div class="mh-middle">可再生资源分类回收大数据平台</div>
      </div>

      <dv-border-box-1 class="main-container">
        <div class="mc-top">
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="累计回收总量" num="123" unit="元" />
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="123" />
          <Top-Left-Cmp name="123" />
        </div>
        <div class="mc-ct">
          <div class="mc-left">
            <div class="mc-left-itm">
              <div class="mc-left-itm-tl">
                <div class="mc-left-itm-tl-lf">回收量</div>
                <div class="mc-left-itm-tl-rt">/公斤</div>
              </div>
              <TopMiddleCmp></TopMiddleCmp>
            </div>
            <div class="mc-left-itm">
              <div class="mc-left-itm-tl">
                <div class="mc-left-itm-tl-lf">新增用户数</div>
                <div class="mc-left-itm-tl-rt">/人</div>
              </div>
              <TopMiddleCmp1></TopMiddleCmp1>
            </div>
            <div class="mc-left-itm flexCloum">
              <div class="mc-left-itm-tl">
                <div class="mc-left-itm-tl-lf">上门回收单数</div>
              </div>
              <div class="mc-left-itm-ct flexRow">
                <div class="order_num">
                  <div class="order_num-hd">
                    <span class="order_num-hd-lf">6,000</span>
                    <span class="order_num-hd-rt">单</span>
                  </div>
                  <div class="order_num-bt">上门回收订单数</div>
                </div>
                <div class="order_num">
                  <div class="order_num-hd">
                    <span class="order_num-hd-lf">6,000</span>
                    <span class="order_num-hd-rt">kg</span>
                  </div>
                  <div class="order_num-bt">上门回收总量</div>
                </div>
                <div class="order_num">
                  <div class="order_num-hd">
                    <span class="order_num-hd-lf">98.5</span>
                    <span class="order_num-hd-rt">%</span>
                  </div>
                  <div class="order_num-bt">上门回收订单数</div>
                </div>
              </div>
            </div>
            <div class="mc-left-itm bottom">
              <div class="mc-left-itm-tl">
                <div class="mc-left-itm-tl-lf">品类分布</div>
              </div>
              <div class="classify">
                <Bottom-Left-Chart-1 />
              </div>
              <div class="classify_ct">
                <div class="classify_lf">
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                </div>
                <div class="classify_rt">
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf"></span>
                    <span class="classify_itm-ct">纸类</span>
                    <span class="classify_itm-rt">20%</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="mc-center">
            <div class="mc-center-hd">
              <div class="mc-center-hd-lf">
                <div class="mc-center-hd-lab">今日回收人次</div>
                <div class="mc-center-hd-num">
                  <span class="mc-center-hd-num-lf">50</span>
                  <span class="mc-center-hd-num-rt">人次</span>
                </div>
              </div>
              <div class="mc-center-hd-ct">
                <div class="mc-center-hd-ct-lab">今日回收总量</div>
                <div class="mc-center-hd-ct-count">
                  <dv-digital-flop
                    :config="config"
                    animationFrame="500"
                    style="width: 200px; height: 50px; padding-top: 20px"
                  />
                  <span class="mc-center-hd-ct-unit">kg</span>
                </div>
              </div>
              <div class="mc-center-hd-rt">
                <div class="mc-center-hd-lab">今日回收金额</div>
                <div class="mc-center-hd-num">
                  <span class="mc-center-hd-num-lf">5000</span>
                  <span class="mc-center-hd-num-rt">元</span>
                </div>
              </div>
            </div>
            <div class="map"></div>
            <div class="ct_bt">
              <div class="ct_bt-tl">实时回收情况</div>
              <dv-scroll-board :config="dataConfig" class="ct_bt-data" />
            </div>
          </div>
          <div class="mc-right">
            <div class="mc-left-itm">
              <div class="mc-left-itm-tl">
                <div class="mc-left-itm-tl-lf">回收时间分布</div>
                <div class="mc-left-itm-tl-rt">/公斤</div>
              </div>
              <TopMiddleCmp2></TopMiddleCmp2>
            </div>
            <div class="mc-left-itm">
              <div class="mc-left-itm-tl">
                <div class="mc-left-itm-tl-lf">近7日回收人数</div>
                <div class="mc-left-itm-tl-rt">/人</div>
              </div>
              <TopMiddleCmp3></TopMiddleCmp3>
            </div>
            <div class="fun3">
              <div class="fun3_itm">
                <div class="mc-left-itm-tl">
                  <div class="mc-left-itm-tl-lf">职业分布</div>
                </div>
                <RadarChart />
              </div>
              <div class="fun3_itm flexCloum">
                <div class="mc-left-itm-tl">
                  <div class="mc-left-itm-tl-lf">门店排行</div>
                </div>
                <div class="rank">
                  <div class="rank_itm">
                    <img class="rank_itm-img" src="./img/ic_second.png" />
                    <div class="rank_itm-tx">2000</div>
                    <div class="rank_itm-bar"></div>
                    <div class="rank_itm-name">格林小城店</div>
                  </div>
                  <div class="rank_itm">
                    <img class="rank_itm-img" src="./img/ic_top.png" />
                    <div class="rank_itm-tx">2000</div>
                    <div class="rank_itm-bar"></div>
                    <div class="rank_itm-name">格林小城店</div>
                  </div>
                  <div class="rank_itm">
                    <img class="rank_itm-img" src="./img/ic_third.png" />
                    <div class="rank_itm-tx">2000</div>
                    <div class="rank_itm-bar"></div>
                    <div class="rank_itm-name">格林小城店</div>
                  </div>
                </div>
              </div>
            </div>
            <div class="fun4">
              <div class="fun4_itm flexCloum">
                <div class="mc-left-itm-tl">
                  <div class="mc-left-itm-tl-lf">回收经理排行</div>
                </div>
                <dv-capsule-chart :config="mRangconfig" class="fun4_rank" />
              </div>
              <div class="fun4_itm">
                <div class="mc-left-itm-tl">
                  <div class="mc-left-itm-tl-lf">投递方式</div>
                </div>
                <Bottom-Left-Chart-2 />
              </div>
            </div>
          </div>
        </div>
        <!-- <div class="mc-bottom">
          <dv-border-box-6 class="bottom-left-container">
            <dv-decoration-4
              class="mcb-decoration-1"
              style="width:5px;height:45%;"
            />
            <dv-decoration-4
              class="mcb-decoration-2"
              style="width:5px;height:45%;"
            />
            <Bottom-Left-Chart-1 />
            <Bottom-Left-Chart-2 />
          </dv-border-box-6>

          <div class="bottom-right-container">
            <Bottom-Right-Table-1 />
            <Bottom-Right-Table-2 />
            <Bottom-Right-Table-3 />
            <Bottom-Right-Table-4 />
          </div>
        </div> -->
      </dv-border-box-1>
    </dv-full-screen-container>
  </div>
</template>

<script>
import TopLeftCmp from "./TopLeftCmp";
import TopMiddleCmp from "./TopMiddleCmp";
import TopMiddleCmp1 from "./TopMiddleCmp1";
import TopMiddleCmp2 from "./TopMiddleCmp2";
import TopMiddleCmp3 from "./TopMiddleCmp3";

import TopRightCmp from "./TopRightCmp";
import RadarChart from "./radarChart";

import BottomLeftChart1 from "./BottomLeftChart1";
import BottomLeftChart2 from "./BottomLeftChart2";

import BottomRightTable1 from "./BottomRightTable1";
import BottomRightTable2 from "./BottomRightTable2";
import BottomRightTable3 from "./BottomRightTable3";
import BottomRightTable4 from "./BottomRightTable4";

function formatter(number) {
  const numbers = number.toString().split("").reverse();
  const segs = [];

  while (numbers.length) segs.push(numbers.splice(0, 3).join(""));

  return segs.join(",").split("").reverse().join("");
}
const config1 = {
  number: [123456],
  content: "{nt}",
  formatter,
  rowGap: 20,
  style: {
    fontSize: 40,
    fontWeight: "bold",
    fill: "#62DEFF",
    lineCap: "butt",
  },
};

const config2 = {
  number: [654321],
  content: "{nt}",
  rowGap: 20,
  formatter,
  style: {
    fontSize: 40,
    fontWeight: "bold",
    fill: "#62DEFF",
    lineCap: "butt",
  },
};

export default {
  name: "DataView",
  components: {
    TopLeftCmp,
    TopMiddleCmp,
    TopMiddleCmp1,
    TopMiddleCmp2,
    TopMiddleCmp3,
    TopRightCmp,
    RadarChart,
    BottomLeftChart1,
    BottomLeftChart2,
    BottomRightTable1,
    BottomRightTable2,
    BottomRightTable3,
    BottomRightTable4,
  },
  data() {
    return {
      config: config1,
      dataConfig: {
        header: ["门店名", "回收品类", "回收金额", "回收时间"],
        headerBGC: "rgba(6, 71, 170, 0.3)",
        oddRowBGC: "rgba(6, 71, 170, 0)",
        evenRowBGC: "rgba(6, 71, 170, 0)",
        rowNum: 4,
        align: ["center", "center", "center", "center"],
        data: [
          ["春天路店", "塑料", "90元", "18:30"],
          ["春天路店", "塑料", "90元", "18:30"],
          ["春天路店", "塑料", "90元", "18:30"],
          ["春天路店", "塑料", "90元", "18:30"],
          ["春天路店", "塑料", "90元", "18:30"],
        ],
      },
      mRangconfig: {
        data: [
          {
            name: "南阳",
            value: 167,
          },
          {
            name: "周口",
            value: 123,
          },
          {
            name: "漯河",
            value: 98,
          },
        ],
        unit: "kg",
        showValue: true,
      },
    };
  },
  mounted() {
    setTimeout(() => {
      this.config = config2;
    }, 2000);
  },
  methods: {
    formatter(number) {
      const numbers = number.toString().split("").reverse();
      const segs = [];

      while (numbers.length) segs.push(numbers.splice(0, 3).join(""));

      return segs.join(",").split("").reverse().join("");
    },
  },
};
</script>

<style lang="less">
#data-view {
  width: 100%;
  height: 100vh;
  background-color: #030409;
  color: #fff;
  box-sizing: border-box;

  #dv-full-screen-container {
    background-image: url("./img/bg.png");
    background-size: 100% 100%;
    box-shadow: 0 0 3px blue;
    display: flex;
    flex-direction: column;
  }

  .main-header {
    height: 10%;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;

    .mh-left {
      font-size: 20px;
      color: rgb(1, 134, 187);

      a:visited {
        color: rgb(1, 134, 187);
      }
    }

    .mh-middle {
      font-size: 30px;
      color: #fff;
      font-weight: bold;
      text-align: center;
      height: 100%;
      line-height: 9vh;
      width: 100%;
      text-shadow: 0px 2px 6px rgba(255, 255, 255, 0.5);
      background-image: url(./img/hd_bg.png);
      background-position: center;
      background-size: 100% 100%;
      background-repeat: no-repeat;
    }

    .mh-left,
    .mh-right {
      width: 450px;
    }
  }

  .main-container {
    height: calc(100vh - 10vh);

    .mc-top,
    .mc-bottom {
      box-sizing: border-box;
      padding: 15px 30px;
      display: flex;
      justify-content: space-between;
    }

    .mc-bottom {
      height: 60%;
    }

    .top-left-cmp,
    .bottom-left-container {
      width: 32%;
    }

    .bottom-left-container {
      position: relative;

      .border-box-content {
        display: flex;
      }

      .mcb-decoration-1,
      .mcb-decoration-2 {
        position: absolute;
        left: 50%;
        margin-left: -2px;
      }

      .mcb-decoration-1 {
        top: 5%;
        transform: rotate(180deg);
      }

      .mcb-decoration-2 {
        top: 50%;
      }

      .bottom-left-chart-1,
      .bottom-left-chart-2 {
        width: 50%;
        height: 100%;
      }
    }

    .bottom-right-container {
      width: 68%;
      padding-left: 30px;
      box-sizing: border-box;
      display: flex;
    }
  }
  .mc-left {
    width: 26%;
    padding-left: 30px;
  }
  .mc-left-itm {
    width: 100%;
    height: 21%;
    background-image: url(./img/left_itm.png);
    background-position: center;
    background-size: 100%;
    background-repeat: no-repeat;
    margin-bottom: 4px;
    &.flexCloum {
      display: flex;
      flex-direction: column;
    }
    &.bottom {
      height: 26%;
      background-image: url(./img/left_bt_bg.png);
      background-position: center;
      background-size: 100%;
      background-repeat: no-repeat;
      margin-bottom: 0;
      position: relative;
    }
  }
  .ct_bt {
    height: 26%;
    background-image: url(./img/ct_bt_bg.png);
    background-position: center;
    background-size: 100%;
    background-repeat: no-repeat;
    margin-bottom: 0;
    position: relative;
    display: flex;
    flex-direction: column;
    .ct_bt-tl {
      height: 40px;
      line-height: 40px;
      text-align: center;
    }
    .ct_bt-data {
      flex: 1;
    }
  }
  .mc-left-itm-tl {
    padding-top: 20px;
    padding-left: 15px;
    padding-right: 15px;
    display: flex;
    align-items: center;
    .mc-left-itm-tl-lf {
      font-size: 18px;
      font-weight: 500;
      color: #d6e6fd;
      line-height: 22px;
      flex: 1;
    }
    .mc-left-itm-tl-rt {
      font-size: 16px;
      font-weight: 400;
      color: #ff9602;
    }
  }

  .mc-left-itm-ct {
    display: flex;
    flex: 1;
    margin-top: 15px;
    align-items: center;
    background: rgba(32, 53, 204, 0.24);
    padding-bottom: 2px;
    .order_num {
      flex: 1;
      height: 90%;
      border-right: 2px solid rgba(98, 222, 255, 0.26);
      &:last-child {
        border-right: none;
      }
      .order_num-hd {
        text-align: center;
        .order_num-hd-lf {
          font-size: 26px;
          color: #ffffff;
          padding-right: 6px;
          font-weight: bold;
        }
        .order_num-hd-rt {
          font-size: 16px;
          color: #ff9602;
        }
      }
      .order_num-bt {
        font-size: 16px;
        color: #d6e6fd;
        line-height: 22px;
        padding-top: 10px;
        text-align: center;
      }
    }
  }
  .classify {
    height: 24%;
    width: 100%;
    position: absolute;
    top: 3px;
    left: 0;
  }
  .classify_ct {
    display: flex;
    .classify_lf {
      padding-left: 3.6%;
      padding-top: 2.7%;
      flex: 1;
    }
    .classify_rt {
      padding-right: 3.6%;
    }
    .classify_itm {
      padding-bottom: 1.4%;
    }
    .classify_itm-lf {
      width: 10px;
      height: 10px;
      background: #4dbaed;
      border-radius: 3px;
      display: inline-block;
      vertical-align: middle;
    }
    .classify_itm-ct {
      font-size: 14px;
      font-weight: 400;
      color: #d6e6fd;
      line-height: 18px;
      vertical-align: middle;
      padding-left: 5px;
    }
    .classify_itm-rt {
      font-size: 16px;
      color: #ffffff;
      line-height: 20px;
      vertical-align: middle;
      padding-left: 5px;
    }
  }
  .mc-ct {
    display: flex;
  }
  .mc-center {
    flex: 1;
    padding: 0 20px;
    .mc-center-hd {
      display: flex;
      .mc-center-hd-lf {
        width: 8.8vw;
        height: 9vh;
        padding-left: 20px;
        text-align: left;
        background-image: url(./img/ctr-top-lf.png);
        background-position: center;
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .mc-center-hd-ct {
        flex: 1;
        text-align: center;
        padding-top: 15px;
        .mc-center-hd-ct-lab {
          font-size: 18px;
          font-weight: 500;
          color: #ffffff;
          line-height: 22px;
        }
        .mc-center-hd-ct-count {
          display: flex;
          justify-content: center;
          align-items: flex-end;
        }
        .mc-center-hd-ct-unit {
          font-size: 24px;
          color: #ffffff;
          line-height: 50px;
        }
      }
      .mc-center-hd-rt {
        width: 8.8vw;
        height: 9vh;
        padding-right: 20px;
        text-align: right;
        background-image: url(./img/ctr-top-rt.png);
        background-position: center;
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .mc-center-hd-lab {
        font-size: 18px;
        font-weight: 500;
        color: #d6e6fd;
        line-height: 22px;
        padding-top: 20px;
      }
      .mc-center-hd-num {
        padding-top: 15px;
        .mc-center-hd-num-lf {
          font-size: 26px;
          font-weight: bold;
          color: #ffffff;
          line-height: 32px;
        }
        .mc-center-hd-num-rt {
          font-size: 16px;
          font-weight: 400;
          color: #ff9602;
          line-height: 20px;
          padding-left: 6px;
        }
      }
    }
  }
  .mc-right {
    width: 26%;
    padding-right: 30px;
  }
  .map {
    height: 30vh;
  }
  .fun3 {
    height: 25%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .fun3_itm {
      width: 48%;
      height: 100%;
      background-image: url(./img/rt_bt_bg3.png);
      background-position: center;
      background-size: 100%;
      background-repeat: no-repeat;
      &.flexCloum {
        display: flex;
        flex-direction: column;
      }
    }
  }
  .fun4 {
    height: 21%;
    margin-top: 10px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .fun4_itm {
      width: 48%;
      height: 100%;
      background-image: url(./img/rt_bt_bg3.png);
      background-position: center;
      background-size: 100% 100%;
      background-repeat: no-repeat;
      &.flexCloum {
        display: flex;
        flex-direction: column;
      }
    }
  }
  .fun4_rank {
    width: 100%;
    flex: 1;
  }
  .rank {
    flex: 1;
    display: flex;
    align-items: flex-end;
    .rank_itm {
      flex: 1;
      width: 0;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      align-items: center;
      .rank_itm-img {
        width: 2rem;
        height: 1.6rem;
        display: block;
      }
      .rank_itm-tx {
        font-size: 14px;
        color: #fff;
        text-align: center;
      }
      .rank_itm-bar {
        width: 0.5rem;
        height: 40px;
        background-image: linear-gradient(#e66465, #9198e5);
        border-radius: 0.5rem;
      }
      .rank_itm-name {
        font-size: 14px;
        color: #fff;
        text-align: center;
        width: 100%;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
    }
  }
}
</style>
