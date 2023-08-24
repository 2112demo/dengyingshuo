<template>
  <div id="box">
    <h3 class="tabbar">
      <i class="iconfont icon-shouye"></i> /
      <span> 首页</span>
    </h3>
    <div class="bottomContent d-flex justify-content-between">
      <div class="left-content">
        <h3>最近项目</h3>
        <ul>
          <li v-for="(item) in oneDemo" :key="item.id">
            <p class="time">{{ item.time }}</p>
            <div>
              <p>项目：<span class="title">{{ item.title }}</span></p>
              <p>进度：<span class="status">{{ item.status }}</span></p>
              <p>订单量：<span class="count">{{ item.count }}</span></p>
              <p>订单额：<span class="sum">{{ item.sum }}</span></p>
            </div>
          </li>
        </ul>
      </div>
      <div class="center-content"></div>
      <div class="right-content"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'index',
  data () {
    return {
      oneDemo: [
        {id: 1, time: '2021-08-25 15:04:09', title: '外卖骑手项目', count: '2', sum: '0.20元', status: '已审核'},
        {id: 2, time: '2021-08-25 16:05:19', title: '外卖骑手项目', count: '1', sum: '0.10元', status: '待报审'},
        {id: 3, time: '2021-08-26 05:04:01', title: '外卖骑手项目', count: '2', sum: '1.00元', status: '已结算'}
      ]
    }
  },
  methods: {
  }
}
</script>

<style>
  #box{
    padding: 10px 0 0 12px;
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
  .bottomContent{
    height: 774px;
    margin-top: 25px;
  }
  .bottomContent div{
    margin-right: 18px;
    flex: 1;
  }
  .bottomContent div:last-child{
    margin-right: 0;
  }
  .left-content{
    background-color: #fff;
    box-shadow: 0 0 20px 0 #e6e6e6;
  }
  .left-content h3{
    height: 60px;
    line-height: 60px;
    border-bottom: 1px solid #e8e8e8;
    font-size: 20px;
    text-indent: 2em;
    color: #212529;
  }
  .left-content ul{
    margin: 18px 15px 0 20px;
    border-left: 2px solid #e4e7ed;
    padding: 0 0 0 15px;
  }
  .left-content ul li{
    margin-top: 30px;
  }
  .left-content ul li .time{
    color: #909399;
    font-size: 12px;
    position: relative;
  }
  .left-content ul li .time::after{
    position: absolute;
    top: 0;
    left: -23px;
    width: 15px;
    height: 15px;
    border-radius: 50%;
    background: #6777ef;
    content: "";
  }
  .left-content ul li div{
    border: 1px solid #ebeef5;
    border-radius: 4px;
    box-shadow: -5px 0 10px 0 #e6e6e6;
    margin-top: 8px;
    padding: 20px 0 20px 15px;
    color: #303133;
  }
  .left-content ul li div .title{
    color: #3a54e2;
  }
  .left-content ul li div .status{
    color: #8400ff;
  }
  .left-content ul li div .count{
    color: #3a54e2;
  }
  .left-content ul li div .sum{
    color: #303133;
  }
  .center-content{
    background-color: #fff;
    box-shadow: 0 0 20px 0 #e6e6e6;
  }
</style>
