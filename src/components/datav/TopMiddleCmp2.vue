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
          data: ['8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20'],
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
          }
        },
        series: [
          {
            data: [2483.8, 2593.7, 525.1, 1901, 399.3, 1135.52, 1849.82, 417.91, 52.5, 147.9, 906.05, 131.2, 807.77],
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
