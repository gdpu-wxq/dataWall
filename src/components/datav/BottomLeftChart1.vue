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
              { name: '监控系统', value: 93 },
              { name: '收费系统', value: 65 },
              { name: '通信系统', value: 32 },
              { name: '供配电系统', value: 44 },
              { name: '其它', value: 52 }
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
        color: ['#00c0ff', '#3de7c9', '#fff', '#00c0ff', '#3de7c9', '#fff']
      }
    }
  }
}
</script>

<style lang="less">
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
