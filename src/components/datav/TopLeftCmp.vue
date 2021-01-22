<template>
  <div class="top-left-cmp">
    <div class="top-left-tp">{{name}}</div>
    <div class="top-left-bt">
      <!-- <span class="top-left-num">{{num}}</span> -->
      <dv-digital-flop
        :config="config"
        style="display:inlne-block; width:100px"
      />
      <span class="top-left-unit">{{unit}}</span>
    </div>
  </div>
</template>

<script>
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
  style: {
    fontSize: 20,
    fontWeight: 'bold',
    fill: '#fff',
    lineCap: 'butt'
  }
}

let config2 = {
  number: [654321],
  content: '{nt}',
  formatter,
  style: {
    fontSize: 20,
    fontWeight: 'bold',
    fill: '#fff',
    lineCap: 'butt'
  }
}
export default {
  name: 'TopLeftCmp',
  props: ['name', 'num', 'unit'],
  data () {
    return {
      config: config1
    }
  },
  mounted () {
    setTimeout(() => {
      console.log(this.num)
      config2.number = [parseFloat(this.num)]
      this.config = config2
    }, 2000)
  }
}
</script>

<style lang="scss">
@import '../../assets/var.scss';
.top-left-cmp {
  width: (100%/8.8);
  height: getHeight(104);
  background-image: url(./img/top_bg.png);
  background-position: center;
  background-size: 100% 100%;
  background-repeat: no-repeat;
  &:last-child{
    margin-right: 0;
  }
}
.top-left-tp{
  text-align: center;
  color: #fff;
  font-size: 16px;
  line-height: 40px;
}
.top-left-bt{
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}
.top-left-num{
  font-size: 20px;
  color: #fff;
}
.top-left-unit{
  color: #ff9602;
  font-size: 14px;
}
</style>
