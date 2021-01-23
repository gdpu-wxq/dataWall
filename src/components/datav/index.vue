<template>
  <div id="data-view">
    <div>
      <div class="main-header">
        <img class="logo" src="./img/logo.png" />
        <div class="mh-middle">可再生资源分类回收大数据平台</div>
        <div class="time">
          <div>
            周{{
              ["日", "一", "二", "三", "四", "五", "六"][new Date().getDay()]
            }}
          </div>
          <div>{{ today }}</div>
        </div>
      </div>

      <div class="main-container">
        <div class="mc-top">
          <Top-Left-Cmp name="门店数" num="5" unit="个" />
          <Top-Left-Cmp name="白龙马经理数" num="26" unit="人" />
          <Top-Left-Cmp name="累计用户数" num="5158" unit="个" />
          <Top-Left-Cmp name="累计订单量" num="21850" unit="单" />
          <Top-Left-Cmp name="累计回收总量" num="2108587.40" unit="kg" />
          <Top-Left-Cmp name="累计中转人次" num="1153" unit="人次" />
          <Top-Left-Cmp name="覆盖小区" num="34" unit="个" />
          <Top-Left-Cmp name="覆盖家庭" num="32196" unit="个" />
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
                    <span class="order_num-hd-lf">5109</span>
                    <span class="order_num-hd-rt">单</span>
                  </div>
                  <div class="order_num-bt">上门回收订单数</div>
                </div>
                <div class="order_num">
                  <div class="order_num-hd">
                    <span class="order_num-hd-lf">421,717.48</span>
                    <span class="order_num-hd-rt">kg</span>
                  </div>
                  <div class="order_num-bt">上门回收总量</div>
                </div>
                <div class="order_num">
                  <div class="order_num-hd">
                    <span class="order_num-hd-lf">98.50</span>
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
                    <span class="classify_itm-rt">49%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf color1"></span>
                    <span class="classify_itm-ct">塑料</span>
                    <span class="classify_itm-rt">21%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf color2"></span>
                    <span class="classify_itm-ct">衣物</span>
                    <span class="classify_itm-rt">7%</span>
                  </div>
                </div>
                <div class="classify_rt">
                  <div class="classify_itm">
                    <span class="classify_itm-lf color3"></span>
                    <span class="classify_itm-ct">五金</span>
                    <span class="classify_itm-rt">8%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf color4"></span>
                    <span class="classify_itm-ct">大件家具</span>
                    <span class="classify_itm-rt">0.10%</span>
                  </div>
                  <div class="classify_itm">
                    <span class="classify_itm-lf color5"></span>
                    <span class="classify_itm-ct">家电3C</span>
                    <span class="classify_itm-rt">3%</span>
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
                  <span class="mc-center-hd-num-lf">{{ person }}</span>
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
                  <span class="mc-center-hd-num-lf">{{ money }}</span>
                  <span class="mc-center-hd-num-rt">元</span>
                </div>
              </div>
            </div>
            <div class="map">
              <img class="map_img" src="./img/img_map.png" />
              <div class="map_tips">
                <div class="map_tips-itm">
                  <span class="map_tips-point"></span
                  ><span class="map_tips-text">营业中</span>
                </div>
                <div class="map_tips-itm">
                  <span class="map_tips-point blue"></span
                  ><span class="map_tips-text">规划中</span>
                </div>
              </div>
            </div>
            <div class="ct_bt">
              <div class="ct_bt-tl">实时回收情况</div>
              <dv-scroll-board
                :config="dataConfig"
                ref="scrollBoard"
                class="ct_bt-data"
              />
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
                    <div class="rank_itm-tx">419157.94</div>
                    <div class="rank_itm-bar second"></div>
                    <div class="rank_itm-name">西平店</div>
                  </div>
                  <div class="rank_itm">
                    <img class="rank_itm-img" src="./img/ic_top.png" />
                    <div class="rank_itm-tx">477876.62</div>
                    <div class="rank_itm-bar"></div>
                    <div class="rank_itm-name">春天店</div>
                  </div>
                  <div class="rank_itm">
                    <img class="rank_itm-img" src="./img/ic_third.png" />
                    <div class="rank_itm-tx">417295.45</div>
                    <div class="rank_itm-bar third"></div>
                    <div class="rank_itm-name">石井店</div>
                  </div>
                </div>
              </div>
            </div>
            <div class="fun4">
              <div class="fun4_itm flexCloum">
                <div class="mc-left-itm-tl">
                  <div class="mc-left-itm-tl-lf">回收经理排行</div>
                </div>
                <div class="fun4_itm-man">
                  <div class="fun4_man-itm">
                    <span class="fun4_man-name">梁绍基</span>
                    <div class="fun4_man-bar">
                      <div class="fun4_man-bar-ct"></div>
                    </div>
                    <span class="fun4_man-num">5082.7</span>
                    <span class="fun4_man-unit">kg</span>
                  </div>
                  <div class="fun4_man-itm">
                    <span class="fun4_man-name">罗祥进</span>
                    <div class="fun4_man-bar">
                      <div class="fun4_man-bar-ct second"></div>
                    </div>
                    <span class="fun4_man-num">3914.55</span>
                    <span class="fun4_man-unit">kg</span>
                  </div>
                  <div class="fun4_man-itm">
                    <span class="fun4_man-name">宋发国</span>
                    <div class="fun4_man-bar">
                      <div class="fun4_man-bar-ct third"></div>
                    </div>
                    <span class="fun4_man-num">3643.25</span>
                    <span class="fun4_man-unit">kg</span>
                  </div>
                </div>
              </div>
              <div class="fun4_itm">
                <div class="mc-left-itm-tl">
                  <div class="mc-left-itm-tl-lf" @click="doUpdate">
                    投递方式
                  </div>
                </div>
                <Bottom-Left-Chart-2 />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TopLeftCmp from './TopLeftCmp'
import TopMiddleCmp from './TopMiddleCmp'
import TopMiddleCmp1 from './TopMiddleCmp1'
import TopMiddleCmp2 from './TopMiddleCmp2'
import TopMiddleCmp3 from './TopMiddleCmp3'

import RadarChart from './radarChart'

import BottomLeftChart1 from './BottomLeftChart1'
import BottomLeftChart2 from './BottomLeftChart2'

function formatter (number) {
  const numbers = number.toString().split('').reverse()
  const segs = []

  while (numbers.length) segs.push(numbers.splice(0, 3).join(''))

  return segs.join(',').split('').reverse().join('')
}
const config1 = {
  number: [0],
  content: '{nt}',
  formatter,
  rowGap: 20,
  style: {
    fontSize: 40,
    fontWeight: 'bold',
    fill: '#62DEFF',
    lineCap: 'butt'
  }
}

let config2 = {
  number: [11929.91],
  content: '{nt}',
  rowGap: 20,
  formatter,
  style: {
    fontSize: 40,
    fontWeight: 'bold',
    fill: '#62DEFF',
    lineCap: 'butt'
  }
}

export default {
  name: 'DataView',
  components: {
    TopLeftCmp,
    TopMiddleCmp,
    TopMiddleCmp1,
    TopMiddleCmp2,
    TopMiddleCmp3,
    RadarChart,
    BottomLeftChart1,
    BottomLeftChart2
  },
  data () {
    return {
      today: '',
      person: 0,
      money: 0,
      weight: 0,
      config: config1,
      dataConfig: {
        header: ['门店名', '回收品类', '回收金额', '回收时间'],
        headerBGC: 'rgba(6, 71, 170, 0.3)',
        oddRowBGC: 'rgba(6, 71, 170, 0)',
        evenRowBGC: 'rgba(6, 71, 170, 0)',
        rowNum: 4,
        align: ['center', 'center', 'center', 'center'],
        data: [
          ['石井店', '黄纸', '326'],
          ['石井店', '塑料', '10.2'],
          ['春天路店', '厚铁', '78.8'],
          ['格林小城店', '衣服', '185'],
          ['春天路店', '拉罐', '0.8'],
          ['格林小城店', '杂铁', '2.8'],
          ['格林小城店', '矿泉水瓶', '4.1'],
          ['春天路店', '中胶', '15.9'],
          ['春天路店', '拉罐', '99.4'],
          ['格林小城店', '中胶', '67.1'],
          ['春天路店', '矿泉水瓶', '62.9'],
          ['格林小城店', '杂铁', '2.4'],
          ['格林小城店', '矿泉水瓶', '9.2'],
          ['春天路店', '杂铁', '11.2'],
          ['格林小城店', '/黄纸', '35.12'],
          ['春天路店', '矿泉水瓶', '3.61'],
          ['格林小城店', '废纸', '2'],
          ['石井店', '花纸', '29.84'],
          ['格林小城店', '杂铁', '11.47'],
          ['格林小城店', '黄纸', '15.8'],
          ['石井店', '拉罐', '6.4'],
          ['格林小城店', '废纸统货', '5.04'],
          ['春天路店', '黄纸', '2.6'],
          ['格林小城店', '黄纸', '13.2'],
          ['石井店', '黄纸', '29.72'],
          ['格林小城店', '/花纸', '29.73'],
          ['春天路店', '废纸', '38.4'],
          ['格林小城店', '黄纸', '14.4'],
          ['春天路店', '花纸', '6.84'],
          ['格林小城店', '中胶', '8.64'],
          ['格林小城店', '废纸', '8.04'],
          ['石井店', '花纸', '61.36'],
          ['格林小城店', '花纸', '16.94'],
          ['石井店', '塑料统货', '77.8'],
          ['格林小城店', '矿泉水瓶', '11.51'],
          ['格林小城店', '冬装', '1.68'],
          ['春天路店', '冬装', '3'],
          ['格林小城店', '衣物统货', '10.87'],
          ['春天路店', '黄纸', '58.49'],
          ['格林小城店', '杂铁', '5.14'],
          ['春天路店', '黄纸', '30'],
          ['石井店', '黄纸', '38.4'],
          ['格林小城店', '废纸统货', '4.08'],
          ['春天路店', '台式电脑', '126.4'],
          ['石井店', '废纸', '28'],
          ['格林小城店', '黄纸', '47.2'],
          ['春天路店', '废纸统货', '19.04'],
          ['格林小城店', '花纸', '45.5'],
          ['春天路店', '废纸统货', '5.06'],
          ['格林小城店', '黄纸', '5'],
          ['春天路店', '黄纸', '6.6'],
          ['格林小城店', '塑料', '7.7'],
          ['格林小城店', '废纸统货', '1449.2'],
          ['春天路店', '废纸统货', '29.07'],
          ['石井店', '杂铁', '9.1'],
          ['石井店', '鞋包', '25.2'],
          ['春天路店', '黄纸', '51.15'],
          ['石井店', '黄纸', '66'],
          ['春天路店', '花纸', '22.45'],
          ['石井店', '花纸', '19.04']
        ]
      },
      mRangconfig: {
        data: [
          {
            name: '梁绍基',
            value: 5082.7
          },
          {
            name: '罗祥进',
            value: 3914.55
          },
          {
            name: '宋发国',
            value: 3643.25
          }
        ],
        unit: 'kg',
        showValue: true,
        colors: ['#4DBAED', '#8C5AF6', '#E677E7']
      }
    }
  },
  mounted () {
    this.today = this.dateFormat('YYYY-mm-dd HH:MM', new Date())
    setInterval(() => {
      this.changeToday()
    }, 5000)
    this.changeData()
  },
  methods: {
    changeToday () {
      // 当天8点时间戳
      let beiginTime =
        new Date(new Date().toLocaleDateString()).getTime() +
        8 * 60 * 60 * 1000
      let endTime =
        new Date(new Date().toLocaleDateString()).getTime() +
        22 * 60 * 60 * 1000
      let nowTime = new Date().getTime()
      let all = 14 * 60 * 60 * 1000
      if (nowTime < beiginTime) {
        this.person = 0
        this.money = 0
        this.weight = 0
      }
      if (beiginTime < nowTime && nowTime < endTime) {
        let during = nowTime - beiginTime
        this.person = parseInt(802 * (during / all))
        this.money = parseFloat(23580.75 * (during / all)).toFixed(2)
        this.weight = parseFloat(11930 * (during / all)).toFixed(2)
      }
      if (nowTime > endTime) {
        this.person = 802
        this.money = 23580.75
        this.weight = 11930
      }
      config2.number = [parseFloat(this.weight)]
      let a = JSON.parse(JSON.stringify(config2))
      this.config = a
      this.today = this.dateFormat('YYYY-mm-dd HH:MM', new Date())
    },
    changeData () {
      let date = new Date()
      let time = this.dateFormat('HH:MM', date)
      this.dataConfig.data.map((item) => {
        if (item.length === 3) {
          item.push(time)
        } else {
          item[3] = time
        }
        return item
      })
    },
    dateFormat (fmt, date) {
      let ret
      const opt = {
        'Y+': date.getFullYear().toString(), // 年
        'm+': (date.getMonth() + 1).toString(), // 月
        'd+': date.getDate().toString(), // 日
        'H+': date.getHours().toString(), // 时
        'M+': date.getMinutes().toString(), // 分
        'S+': date.getSeconds().toString() // 秒
        // 有其他格式化字符需求可以继续添加，必须转化成字符串
      }
      for (let k in opt) {
        ret = new RegExp('(' + k + ')').exec(fmt)
        if (ret) {
          fmt = fmt.replace(
            ret[1],
            ret[1].length === 1 ? opt[k] : opt[k].padStart(ret[1].length, '0')
          )
        }
      }
      return fmt
    },
    doUpdate (rows) {
      this.$refs['scrollBoard'].updateRows(rows)
    },
    formatter (number) {
      const numbers = number.toString().split('').reverse()
      const segs = []

      while (numbers.length) segs.push(numbers.splice(0, 3).join(''))

      return segs.join(',').split('').reverse().join('')
    }
  }
}
</script>

<style lang="scss">
@import "../../assets/var.scss";

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
    height: getHeight(103);
    display: flex;
    align-items: center;
    background-image: url(./img/hd_bg.png);
    background-position: center;
    background-size: 100% 100%;
    background-repeat: no-repeat;
    width: 100%;
    .mh-middle {
      font-size: getWidth(30);
      color: #fff;
      flex: 1;
      font-weight: bold;
      text-align: center;
      height: 100%;
      line-height: getHeight(90);
      text-shadow: 0px 2px 6px rgba(255, 255, 255, 0.5);
    }
  }

  .main-container {
    height: calc(100vh - getHeight(103));
    .mc-top {
      box-sizing: border-box;
      padding: getHeight(15) getWidth(30);
      display: flex;
      justify-content: space-between;
    }
  }
  .mc-left {
    width: getWidth(512);
    padding-left: getWidth(30);
  }
  .mc-left-itm {
    width: 100%;
    height: getHeight(175);
    background-image: url(./img/left_itm.png);
    background-position: center;
    background-size: 100% 100%;
    background-repeat: no-repeat;
    margin-bottom: getHeight(15);
    &.flexCloum {
      display: flex;
      flex-direction: column;
    }
    &.bottom {
      height: getHeight(190);
      background-image: url(./img/left_bt_bg.png);
      background-position: center;
      background-size: 100% 100%;
      background-repeat: no-repeat;
      margin-bottom: 0;
      position: relative;
    }
  }
  .ct_bt {
    height: getHeight(215);
    background-image: url(./img/ct_bt_bg.png);
    background-position: center;
    background-size: 100% 100%;
    background-repeat: no-repeat;
    margin-bottom: 0;
    position: relative;
    display: flex;
    flex-direction: column;
    .ct_bt-tl {
      height: getHeight(60);
      line-height: getHeight(60);
      font-size: getWidth(18);
      text-align: center;
    }
    .ct_bt-data {
      flex: 1;
    }
  }
  .mc-left-itm-tl {
    padding-top: getHeight(20);
    padding-left: getWidth(15);
    padding-right: getWidth(15);
    display: flex;
    align-items: center;
    .mc-left-itm-tl-lf {
      font-size: getWidth(18);
      font-weight: 500;
      color: #d6e6fd;
      flex: 1;
    }
    .mc-left-itm-tl-rt {
      font-size: getWidth(16);
      font-weight: 400;
      color: #ff9602;
    }
  }

  .mc-left-itm-ct {
    display: flex;
    flex: 1;
    margin-top: getHeight(15);
    align-items: center;
    background: rgba(32, 53, 204, 0.24);
    padding-bottom: 2px;
    .order_num {
      flex: 1;
      height: getHeight(70);
      border-right: 2px solid rgba(98, 222, 255, 0.26);
      &:last-child {
        border-right: none;
      }
      .order_num-hd {
        text-align: center;
        .order_num-hd-lf {
          font-size: getWidth(24);
          color: #ffffff;
          padding-right: 6px;
          font-weight: bold;
        }
        .order_num-hd-rt {
          font-size: getWidth(16);
          color: #ff9602;
        }
      }
      .order_num-bt {
        font-size: getWidth(16);
        color: #d6e6fd;
        padding-top: getHeight(10);
        text-align: center;
      }
    }
  }
  .classify {
    height: getHeight(210);
    width: 100%;
    position: absolute;
    top: 3px;
    left: 0;
  }
  .classify_ct {
    display: flex;
    .classify_lf {
      padding-left: getWidth(60);
      padding-top: getHeight(30);
      flex: 1;
    }
    .classify_rt {
      padding-right: getWidth(30);
    }
    .classify_itm {
      padding-bottom: getHeight(15);
    }
    .classify_itm-lf {
      width: getWidth(10);
      height: getWidth(10);
      background: #4dbaed;
      border-radius: 3px;
      display: inline-block;
      vertical-align: middle;
      &.color1 {
        background: #8c5af6;
      }
      &.color2 {
        background: #e677e7;
      }
      &.color3 {
        background: #50c8a8;
      }
      &.color4 {
        background: #afd14e;
      }
      &.color5 {
        background: #d3b239;
      }
    }
    .classify_itm-ct {
      font-size: getWidth(14);
      font-weight: 400;
      color: #d6e6fd;
      vertical-align: middle;
      padding-left: 5px;
    }
    .classify_itm-rt {
      font-size: getWidth(16);
      color: #ffffff;
      vertical-align: middle;
      padding-left: 5px;
    }
  }
  .mc-ct {
    display: flex;
    width: 100%;
    box-sizing: border-box;
  }
  .mc-center {
    width: getWidth(840);
    box-sizing: border-box;
    padding: 0 getWidth(20);
    display: flex;
    flex-direction: column;
    .mc-center-hd {
      display: flex;
      .mc-center-hd-lf {
        width: getWidth(190);
        height: getHeight(105);
        padding-left: getWidth(20);
        text-align: left;
        background-image: url(./img/ctr-top-lf.png);
        background-position: center;
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .mc-center-hd-ct {
        flex: 1;
        text-align: center;
        padding-top: getHeight(15);
        .mc-center-hd-ct-lab {
          font-size: getWidth(18);
          font-weight: 500;
          color: #ffffff;
        }
        .mc-center-hd-ct-count {
          display: flex;
          justify-content: center;
          align-items: flex-end;
        }
        .mc-center-hd-ct-unit {
          font-size: getWidth(24);
          color: #ffffff;
          line-height: getHeight(50);
        }
      }
      .mc-center-hd-rt {
        width: getWidth(175);
        height: getHeight(105);
        padding-right: getWidth(20);
        text-align: right;
        background-image: url(./img/ctr-top-rt.png);
        background-position: center;
        background-size: 100% 100%;
        background-repeat: no-repeat;
      }
      .mc-center-hd-lab {
        font-size: getWidth(18);
        font-weight: 500;
        color: #d6e6fd;
        padding-top: getHeight(18);
      }
      .mc-center-hd-num {
        padding-top: getHeight(15);
        .mc-center-hd-num-lf {
          font-size: getWidth(26);
          font-weight: bold;
          color: #ffffff;
        }
        .mc-center-hd-num-rt {
          font-size: getWidth(16);
          font-weight: 400;
          color: #ff9602;
          padding-left: 6px;
        }
      }
    }
  }
  .mc-right {
    width: getWidth(512);
    padding-right: getWidth(30);
  }
  .fun3 {
    height: getHeight(200);
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .fun3_itm {
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
  .fun4 {
    height: getHeight(175);
    margin-top: getHeight(15);
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
    width: 80%;
    flex: 1;
    font-size: getWidth(14);
  }
  .rank {
    flex: 1;
    display: flex;
    align-items: flex-end;
    padding-bottom: getWidth(8);
    .rank_itm {
      flex: 1;
      width: 0;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      align-items: center;
      .rank_itm-img {
        width: getWidth(38);
        height: getheight(33);
        display: block;
      }
      .rank_itm-tx {
        font-size: getWidth(14);
        color: #fff;
        text-align: center;
      }
      .rank_itm-bar {
        width: getWidth(8);
        height: getHeight(60);
        background-image: linear-gradient(270deg, #ffb3d4 0%, #bf4677 100%);
        border-radius: getWidth(4);
        &.second {
          height: getHeight(45);
          background-image: linear-gradient(270deg, #9bcfff 0%, #296bdc 100%);
        }
        &.third {
          height: getHeight(30);
          background-image: linear-gradient(270deg, #c7e7ce 0%, #639b68 100%);
        }
      }
      .rank_itm-name {
        font-size: getWidth(14);
        color: #fff;
        text-align: center;
        width: 100%;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
    }
  }
  .map {
    flex: 1;
    position: relative;
    padding-top: getWidth(20);

    .map_img {
      width: getWidth(620);
      margin: 0 auto;
      display: block;
    }
    .map_tips {
      position: absolute;
      bottom: 30px;
      left: 30px;
    }
    .map_tips-point {
      width: 10px;
      height: 10px;
      display: inline-block;
      vertical-align: middle;
      background: #ff9100;
      border-radius: 5px;
      &.blue {
        background: #1faae1;
      }
    }
    .map_tips-text {
      font-size: getWidth(14);
      color: #9bcfff;
      vertical-align: middle;
      padding-left: 10px;
    }
  }
  .logo {
    display: inline-block;
    width: getWidth(140);
    height: getHeight(50);
    margin-left: getWidth(200);
  }
  .time {
    width: getWidth(140);
    font-size: getWidth(14);
    text-align: right;
    margin-right: getWidth(200);
  }
  .fun4_itm-man {
    width: 100%;
    box-sizing: border-box;
    padding: getWidth(15);
    font-size: getWidth(14);
    padding-top: getHeight(20);
  }
  .fun4_man-itm {
    display: flex;
    margin-bottom: getHeight(20);
    align-items: center;
  }
  .fun4_man-name {
    color: #9bcfff;
    padding-right: 4px;
  }
  .fun4_man-bar {
    flex: 1;
    height: getWidth(8);
    padding: 0;
    margin: 0;
    border-radius: getWidth(4);
    background: rgba(255, 255, 255, 0.3);
  }
  .fun4_man-bar-ct {
    border-radius: getWidth(4);
    height: 100%;
    width: 80%;
    background-image: linear-gradient(270deg, #ffb3d4 0%, #bf4677 100%);
    &.second {
      width: 50%;
      background-image: linear-gradient(270deg, #9bcfff 0%, #296bdc 100%);
    }
    &.third {
      width: 40%;
      background-image: linear-gradient(270deg, #c7e7ce 0%, #639b68 100%);
    }
  }
  .fun4_man-num {
    color: #fff;
    padding-left: 4px;
  }
  .fun4_man-unit {
    padding-left: 4px;
    color: #ff9100;
  }
}
</style>
