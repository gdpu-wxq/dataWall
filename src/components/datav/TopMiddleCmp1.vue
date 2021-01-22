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
          bottom: 50
        },
        xAxis: {
          data: [
            '01/14', '01/15', '01/16', '01/17', '01/18', '01/19', '01/20'
          ],
          boundaryGap: false,
          axisLine: {
            style: {
              stroke: '#fff'
            }
          },
          axisLabel: {
            style: {
              fill: '#fff'
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
          }
        },
        series: [
          {
            data: [130, 155, 147, 158, 163, 149, 178],
            type: 'line',
            smooth: true,
            lineArea: {
              show: true,
              gradient: ['rgba(55, 162, 218, 0.6)', 'rgba(55, 162, 218, 0)']
            },
            label: {
              show: true,
              style: {
                fill: '#fff'
              }
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

<style lang="less" scoped>
.top-middle-cmp {
  position: relative;
  width: 100%;
  height: 13vh;
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
