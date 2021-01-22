<template>
  <div class="bottom-left-chart-1">
    <dv-charts :option="option" />
  </div>
</template>

<script>
const option1 = {
  grid: {
    top: 50,
    bottom: 30
  },
  radar: {
    indicator: [
      { name: '职业收卖', max: 50 },
      { name: '普通居民', max: 50 },
      { name: '商铺', max: 50 },
      { name: '保洁员', max: 50 }
    ],
    polygon: true,
    axisLine: {
      style: {
        stroke: 'rgba(237, 156, 80, .7)'
      }
    },
    axisLabel: {
      labelGap: 5,
      style: {
        fill: '#fff'
      }
    },
    splitLine: {
      style: {
        stroke: 'rgba(237, 156, 80, 0.5)',
        fill: 'rgba(237, 156, 80, .2)'
      }
    }
  },
  series: [
    {
      type: 'radar',
      data: [20, 40, 10, 30],
      label: {
        show: false,
        style: {
          fill: '#fff'
        }
      },
      point: {
        show: false
      },
      radarStyle: {
        fill: 'rgba(237, 156, 80, .7)',
        stroke: 'rgba(237, 156, 80, .7)'
      }
    }
  ]
}
export default {
  name: 'BottomLeftChart3',
  data () {
    return {
      option: option1
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../../assets/var.scss';
.bottom-left-chart-1 {
  position: relative;
  width: 100%;
  height: getHeight(140);
  box-sizing: border-box;
}
</style>
