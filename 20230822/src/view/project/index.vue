<template>
  <div id="box">
    <h3 class="tabbar">
      <i class="iconfont icon-shouye"></i> /
      <span> 首页 / 项目任务 / 批量新建订单</span>
    </h3>
    <div class="mainer">
      <div class="top-box d-flex justify-between">
        <div class="d-flex align-center top-h1-box active">
          <h1 class="top-h1">01</h1>
          <div>
            <h3 class="top-h3">项目信息</h3>
            <p class="top-p">项目名称、类型、预算等</p>
          </div>
        </div>
        <div class="speed d-flex justify-between align-center">
          <span></span><span class="active"></span><span></span>
        </div>
        <div class="d-flex align-center top-h1-box">
          <h1 class="top-h1">02</h1>
          <div>
            <h3 class="top-h3">人员导入</h3>
            <p class="top-p">批量导入人员数据</p>
          </div>
        </div>
        <div class="speed d-flex justify-between align-center">
          <span></span><span class="active"></span><span></span>
        </div>
        <div class="d-flex align-center top-h1-box">
          <h1 class="top-h1">03</h1>
          <div>
            <h3 class="top-h3">数据校验</h3>
            <p class="top-p">检查数据是否有误</p>
          </div>
        </div>
      </div>
      <div class="input-box">
        <form action="">
          <div class="inp-p">
            <label for="inp-type">任务类型</label>
            <el-select id="inp-type" size="small" v-model="value" placeholder="请选择任务类型">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
          </div>
          <div class="inp-p">
            <label for="inp-save">省份</label>
            <el-select id="inp-save" size="small" v-model="value" placeholder="请选择省">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
            <span class="last-time">(上一次的选择是<a href="">河北省</a>)</span>
          </div>
          <div class="inp-p">
            <label for="inp-city">城市</label>
            <el-select id="inp-city" size="small" v-model="value" placeholder="请选择市">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
              </el-option>
            </el-select>
          </div>
          <div class="inp-p">
            <label>项目时间</label>
            <div class="block">
              <el-date-picker
                size="small"
                v-model="value1"
                type="daterange"
                range-separator="至"
                start-placeholder="开始日期"
                end-placeholder="结束日期">
              </el-date-picker>
            </div>
          </div>
          <div class="inp-p">
            <label for="demo-name">项目名称</label>
            <el-input id="demo-name" size="small" v-model="input" placeholder="请输入"></el-input>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'project',
  data () {
    return {
      msg: '这是一个vue项目模板',
      options: [{
        value: '选项1',
        label: '黄金糕'
      }, {
        value: '选项2',
        label: '双皮奶'
      }, {
        value: '选项3',
        label: '蚵仔煎'
      }, {
        value: '选项4',
        label: '龙须面'
      }, {
        value: '选项5',
        label: '北京烤鸭'
      }],
      value: '',
      pickerOptions: {
        shortcuts: [{
          text: '最近一周',
          onClick (picker) {
            const end = new Date()
            const start = new Date()
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 7)
            picker.$emit('pick', [start, end])
          }
        }, {
          text: '最近一个月',
          onClick (picker) {
            const end = new Date()
            const start = new Date()
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 30)
            picker.$emit('pick', [start, end])
          }
        }, {
          text: '最近三个月',
          onClick (picker) {
            const end = new Date()
            const start = new Date()
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 90)
            picker.$emit('pick', [start, end])
          }
        }]
      },
      value1: '',
      input: ''
    }
  },
  methods: {
  }
}
</script>

<style lang="less">
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
    margin-top: 15px;
    height: calc(100vh - 63px);
    box-shadow: 0 0 20px 0 #e6e6e6;
    border-radius: 5px;
    padding: 30px 18px 0;
    .top-box{
      height: 156px;
      border-bottom: 1px solid #e8e8e8;
      box-sizing: border-box;
      .top-h1-box.active{
        color: #d0121b;
      }
      .top-h1-box{
        color: #999999;
        .top-h1{
          font-size: 90px;
          font-weight: 600;
          font-family: "楷体";
        }
        .top-h3{
          font-size: 22px;
          font-weight: 600;
        }
        .top-p{
          font-size: 16px;
        }
      }
      .speed{
        width: 50px;
      }
      .speed span{
        display: inline-block;
        width: 10px;
        height: 10px;
        background: #999999;
        border-radius: 50%;
      }
      .speed span.active{
        width: 13px;
        height: 13px;
      }
    }
    .top-box div:last-child{
      margin-right: 50px;
    }
    .input-box{
      padding: 20px 0 0 38px;
      .inp-p{
        margin-top: 23px;
        display: flex;
        align-items: center;
        width: 450px;
        .last-time{
          margin-left: 10px;
        }
        .last-time a{
          color: #2c4198;
          text-decoration: underline;
        }
      }
      .inp-p label{
        text-align: right;
        margin-right: 10px;
        display: inline-block;
        width: 90px;
      }
    }
  }
</style>
