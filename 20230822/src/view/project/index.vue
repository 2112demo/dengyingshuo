<template>
  <div id="box">
    <h3 class="tabbar">
      <i class="iconfont icon-shouye"></i> /
      <span> 首页 / 项目任务 / 批量新建订单</span>
    </h3>
    <div class="mainer">
    </div>
  </div>
</template>

<script>
export default {
  name: 'project',
  data () {
    return {
      msg: '这是一个vue项目模板'
    }
  },
  methods: {
  }
}
</script>

<style>
  #box{
    padding: 10px 0 0 0;
  }
  .tabbar{
    padding-left: 10px;
    font-size: 14px;
    color: #616870;
  }
  .tabbar i{
    font-size: 26px;
    color: #2c4198;
  }
  .tabbar span{
    font-weight: 500;
    color: #616870;
    font-size: 13px;
  }
  .mainer{
    background: #fff;
    height: 100px;
    box-shadow: 0 0 20px 0 #e6e6e6;
    border-radius: 5px;
  }
</style>
