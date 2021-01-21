<template>
  <div class="bottom-left-chart-1">
    <dv-charts :option="option" />
  </div>
</template>

<script>
const option1 = {
  radar: {
    indicator: [
      { name: "西峡", max: 300 },
      { name: "周口", max: 300 },
      { name: "南阳", max: 300 },
      { name: "驻马店", max: 300 },
    ],
    polygon: true,
    axisLine: {
      style: {
        stroke: "rgba(237, 156, 80, .7)",
      },
    },
    axisLabel: {
      style: {
        fill: "#fff",
      },
    },
    splitLine: {
      style: {
        stroke: "rgba(237, 156, 80, 0.5)",
        fill: "rgba(237, 156, 80, .2)",
      },
    },
  },
  series: [
    {
      type: "radar",
      data: [111, 256, 178, 152],
      label: {
        style: {
          fill: "#fff",
        },
      },
      point:{
        show: false
      },
      radarStyle: {
        fill: "rgba(237, 156, 80, .7)",
        stroke: 'rgba(237, 156, 80, .7)'
    }
    },
  ],
};

const option2 = {
  radar: {
    indicator: [
      { name: "西峡", max: 300 },
      { name: "周口", max: 300 },
      { name: "南阳", max: 300 },
      { name: "驻马店", max: 300 },
      { name: "郑州", max: 300 },
      { name: "洛阳", max: 300 },
    ],
    polygon: true,
    axisLine: {
      style: {
        stroke: "rgba(230, 114, 209, .3)",
      },
    },
    splitLine: {
      style: {
        stroke: "rgba(230, 114, 209, .5)",
        fill: "rgba(230, 114, 209, .2)",
      },
    },
  },
  series: [
    {
      type: "radar",
      data: [223, 189, 214, 265, 178, 155],
    },
  ],
};
export default {
  name: "BottomLeftChart3",
  data() {
    return {
      option: option1,
    };
  },
};
</script>

<style lang="less" scoped>
.bottom-left-chart-1 {
  position: relative;
  width: 100%;
  height: 100px;
  box-sizing: border-box;
}
</style>
