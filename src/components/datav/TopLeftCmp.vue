<template>
  <div class="top-left-cmp">
    <div class="top-left-tp">{{name}}</div>
    <div class="top-left-bt"><span class="top-left-num">{{num}}</span><span class="top-left-unit">{{unit}}</span></div>
  </div>
</template>

<script>
export default {
  name: 'TopLeftCmp',
  props: ['name', 'num', 'unit']
}
</script>

<style lang="less">
.top-left-cmp {
  width: 200px;
  height: 100px;
  margin-right: 20px;
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
  margin-top: 16px;
}
.top-left-num{
  font-size: 20px;
  color: #fff;
}
.top-left-unit{
  color: #ff9602;
  font-size: 14px;
  padding-left: 4px;
}
</style>
