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
        grid: {
          top: 0,
          left: 30,
          right: 30,
          bottom: 0
        },
        series: [
          {
            type: 'pie',
            radius: ['35%', '65%'],
            data: [
              { name: '监控系统', value: 93 },
              { name: '收费系统', value: 65 },
            ],
            outsideLabel: {
              labelLineEndLength: 10,
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

<style lang="less" scoped>
.bottom-left-chart-1 {
  position: relative;
  width: 100%;
  height: 100px;
  box-sizing: border-box;

 

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
