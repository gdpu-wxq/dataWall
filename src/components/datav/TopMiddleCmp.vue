<template>
  <div class="top-middle-cmp">
    <dv-charts :option="option" />
  </div>
</template>

<script>
export default {
  name: 'TopMiddleCmp',
  data () {
    return {
      option: {
        legend: {
          show: false
        },
        grid: {
          top: 20,
          left: 30,
          right: 30,
          bottom: 70
        },
        xAxis: {
          data: [
            '10/01', '10/02', '10/03', '10/04', '10/05', '10/06',
            '10/07', '10/07', '10/08'
          ],
          boundaryGap: false,
          axisLine: {
            style: {
              stroke: '#999'
            }
          },
          axisLabel: {
            style: {
              fill: '#999'
            }
          },
          axisTick: {
            show: false
          }
        },
        yAxis: {
          data: 'value',
          splitLine: {
            show: false
          },
          axisLine: {
            show: false,
            style: {
              stroke: '#999'
            }
          },
          axisLabel: {
            show: false
          },
          axisTick: {
            show: false
          },
          min: 95,
          max: 100,
          interval: 0.5
        },
        series: [
          {
            data: [
              99.56, 99.66, 99.84, 99.22, 99.11, 99.45,
              99.44, 99.81, 99.84
            ],
            type: 'line',
            smooth: true,
            lineArea: {
              show: true,
              gradient: ['rgba(55, 162, 218, 0.6)', 'rgba(55, 162, 218, 0)']
            },
            label: {
              show: true
            }
            // linePoint: {
            //   radius: 4,
            //   style: {
            //     fill: '#00db95'
            //   }
            // }
          }
        ]
      }
    }
  }
}
</script>

<style lang="less">
.top-middle-cmp {
  position: relative;
  width: 100%;
  height: 100%;
  box-sizing: border-box;

  .chart-name {
    position: absolute;
    right: 70px;
    text-align: right;
    font-size: 20px;
    top: 10px;
  }
}
</style>
