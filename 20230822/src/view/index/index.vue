<template>
  <div id="box">
    <hotSearch></hotSearch>
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
      <div class="center-content">
        <h3>资金动态</h3>
        <ul>
          <li v-for="item in twoDemo" :key="item.id">
            <i class="iconfont icon-gengduo"></i>
            <span>{{ item.title }}</span>
            <span :style="{color: item.title === '充值' ? 'red' : '#28c76f'}">{{ item.sum }}</span>
          </li>
        </ul>
      </div>
      <div class="right-content">
        <div class="word-box d-flex justify-between align-center">
          <img src="../../assets/logo.png" alt="">
          <p>
            <span>批量打款</span>
            <span>批量订单快速到账</span>
          </p>
        </div>
        <div class="excel-box d-flex justify-between align-center">
          <img src="../../assets/logo.png" alt="">
          <p>
            <span>模板下载</span>
            <span>批量下发的Excel模板</span>
          </p>
        </div>
        <div class="link-box">
          <h3>快速链接</h3>
          <ul>
            <li><a href="">项目列表</a></li>
            <li><a href="">订单列表</a></li>
            <li><a href="">异常订单</a></li>
            <li><a href="">发票申请</a></li>
            <li><a href="">交易明细</a></li>
            <li><a href="">专属账户</a></li>
            <li><a href="">企业信息</a></li>
            <li><a href="">账号密码</a></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import hotSearch from './childrens/hotSearch'
export default {
  name: 'index',
  components: {
    // 组件名: 组件 hotSearch变成自定义标签
    'hotSearch': hotSearch
  },
  data () {
    return {
      oneDemo: [
        {id: 1, time: '2021-08-25 15:04:09', title: '外卖骑手项目', count: '2', sum: '0.20元', status: '已审核'},
        {id: 2, time: '2021-08-25 16:05:19', title: '外卖骑手项目', count: '1', sum: '0.10元', status: '待报审'},
        {id: 3, time: '2021-08-26 05:04:01', title: '外卖骑手项目', count: '2', sum: '1.00元', status: '已结算'}
      ],
      twoDemo: [
        {id: 1, title: '平台结算', sum: '-0.20'},
        {id: 2, title: '平台结算', sum: '-0.20'},
        {id: 3, title: '充值', sum: '+2.00'},
        {id: 4, title: '平台结算', sum: '-0.20'},
        {id: 5, title: '平台结算', sum: '-0.20'},
        {id: 6, title: '充值', sum: '+1.00'},
        {id: 7, title: '平台结算', sum: '-0.20'},
        {id: 8, title: '平台结算', sum: '-0.20'},
        {id: 9, title: '充值', sum: '+0.10'}
      ]
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
  .bottomContent{
    height: 774px;
    margin-top: 25px;
    overflow-x: hidden;
  }
  .bottomContent>div{
    margin-right: 18px;
    flex: 1;
  }
  .bottomContent>div:last-child{
    margin-right: 10px;
  }
  .left-content{
    background-color: #fff;
    box-shadow: 0 0 20px 0 #e6e6e6;
    border-radius: 5px;
  }
  .left-content h3,.center-content h3,.link-box h3{
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
    border-radius: 5px;
  }
  .center-content ul{
    margin: 20px 10px 0 20px;
  }
  .center-content ul li{
    height: 40px;
    box-sizing: border-box;
    border-top: 1px solid #ebeef5;
    line-height: 40px;
    padding: 0 12px 0 18px;
    display: flex;
    color: #606266;
    font-size: 13px;
  }
  .center-content ul li i{
    margin-right: 36px;
  }
  .center-content ul li span:last-child{
    margin-left: auto;
    color: #28c76f;
  }
  .right-content{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .right-content div{
    /* width: 100%; */
    height: 150px;
    margin-bottom: 26px;
    background: #fff;
    box-shadow: 0 0 10px 0 #e6e6e6;
    border-radius: 5px;
  }
  .right-content div:last-child{
    flex: 1;
    margin-bottom: 0;
  }
  .word-box,.excel-box{
    padding: 0 24px 0 38px;
  }
  .word-box img,.excel-box img{
    width: 65px;
    height: 74px;
  }
  .word-box p,.excel-box p{
    height: 74px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    text-align: right;
    font-weight: bold;
  }
  .word-box p span,.excel-box p span{
    font-size: 22px;
    color: #353c48;
  }
  .word-box p span:last-child,.excel-box p span:last-child{
    font-size: 16px;
    color: #3a54e2;
  }
  .link-box ul{
    padding: 22px 12px 0 16px;
    display: flex;
    flex-wrap: wrap;
    flex: 3;
  }
  .link-box ul li{
    margin-bottom: 15px;
    margin-right: 12px;
    border: 1px solid #dddfe5;
    border-radius: 5px;
    width: 30%;
    height: 50px;
    line-height: 50px;
    box-sizing: border-box;
    text-align: center;
    background-color: #f5f6fa;
  }
  .link-box ul li:last-child{
  }
</style>
