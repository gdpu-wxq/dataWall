<template>
  <div class="bottom-left-chart-1">
    <dv-charts :option="option" />
  </div>
</template>

<script>
export default {
  name: 'BottomLeftChart1',
  data () {
    return {
      option: {
        legend: {
          show: true
        },
        grid: {
          top: 0,
          left: 30,
          right: 30,
          bottom: 0
        },
        series: [
          {
            type: 'pie',
            data: [
              { name: '纸类', value: 49 },
              { name: '塑料', value: 21 },
              { name: '衣物', value: 7 },
              { name: '五金', value: 8 },
              { name: '大件家具', value: 0.10 },
              { name: '家电3C', value: 3 }
            ],
            outsideLabel: {
              show: false,
              labelLineEndLength: 20,
              formatter: '{percent}%\n{name}',
              style: {
                fill: '#fff'
              }
            }
          }
        ],
        color: ['#4DBAED', '#8C5AF6', '#E677E7', '#50C8A8', '#AFD14E', '#D3B239', '#D88055']
      }
    }
  }
}
</script>

<style lang="less" scoped>
.bottom-left-chart-1 {
  position: relative;
  width: 100%;
  height: 210px;
  box-sizing: border-box;

  .header-name {
    height: 150px;
    line-height: 150px;
    font-size: 20px;
    text-align: center;
  }

  .details-value {
    height: 40px;
    font-size: 30px;
    font-weight: bold;
    text-align: center;

    span {
      color: #00c0ff;
      font-size: 45px;
    }
  }

  .decoration-ring {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    border: 5px solid fade(#fefefe, 30);
    top: 190px;
    left: 50%;
    transform: translateX(-50%);
  }
}
</style>
