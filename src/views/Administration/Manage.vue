<template>
  <div class="format adminLayout">
    <el-card class="box-card adminCard">
      <div slot="header" class="clearfix">
        <span>班级管理</span>
        <el-button icon="el-icon-menu" size="small" class="adminButton" style="float: right; padding: 5px" type="text">所有班级</el-button>
      </div>
      <div class="adminConter">
        <div class="adminConterTop">
          <div>
            <el-button @click="adminButton('按校区查找')" type="info" icon="el-icon-edit" circle></el-button>
            <p>按校区查找</p>
          </div>
          <div>
            <el-button @click="adminButton('按教师查找')" type="info" conter="123" icon="el-icon-edit" circle></el-button>
            <p>按教师查找</p>
          </div>
          <div>
            <el-button @click="adminButton('按首课日期查找')" type="info" icon="el-icon-edit" circle></el-button>
            <p>按首课日期查找</p>
          </div>
          <div>
            <el-button @click="adminButton('按班级续费提醒')" type="info" icon="el-icon-edit" circle></el-button>
            <p>按班级续费提醒</p>
          </div>
          <div>
            <el-button @click="adminButton('按班级状态查找')" type="info" icon="el-icon-edit" circle></el-button>
            <p>按班级状态查找</p>
          </div>
          <div>
            <el-button @click="adminButton('按教室查找')" type="info" icon="el-icon-edit" circle></el-button>
            <p>按教室查找</p>
          </div>
          <div>
            <el-button @click="adminButton('按课程查找')" type="info" icon="el-icon-edit" circle></el-button>
            <p>按课程查找</p>
          </div>
          <div class="synthesize">
            <el-button icon="el-icon-search" circle />
            <p>综合检索</p>
          </div>
        </div>
        <div>
          <el-select v-model="value" filterable :placeholder="selecthodel">
            <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            />
          </el-select>
        </div>
      </div>
    </el-card>
    <el-card class="box-card adminCard">
      <div slot="header" class="clearfix">
        <span>学员管理</span>
        <el-button icon="el-icon-menu" size="small" class="adminButton" style="float: right; padding: 5px" type="text">所有学员</el-button>
      </div>
      123
    </el-card>
    <el-card class="box-card adminCard">
      <div slot="header" class="clearfix">
        <span>师资管理</span>
        <el-button icon="el-icon-menu" size="mini" class="adminButton" style="float: right; padding: 5px" type="text">所有师资</el-button>
      </div>
      123
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'Manage',
  data() {
    return {
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
      selecthodel: '按校区查找'
    }
  },
  methods: {
    adminButton(value) {
      console.log(value)
      this.selecthodel = value
    }
  }
}
</script>

<style >
  .adminLayout{
    display: flex;
    justify-content: space-around;
  }
  .adminCard{
    min-height: 200px;
    width: 32%;
    border-radius: 5%;
  }
  .adminCard .el-card__header{
    border-bottom: 0;
  }
  .adminButton{
    border: 1px solid #EB9B36;
    padding: 5px;
  }
  .adminConter>.adminConterTop{
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
    position: relative;
  }
  .adminConter>.adminConterTop>div{
    width: 20%;
    font-size: 12px;
    text-align: center;
  }
  .adminConter>.adminConterTop>div>p{
    padding: 0 10px;
  }
  .adminConter .el-button--info:hover, .el-button--info:focus{
    box-shadow: 0 0 0 2px #fff, 0 0 0 4px #EB9B36;
  }
  .synthesize{
    color: #999;
    position: absolute;
    right: 0;
    bottom: 0;
  }
</style>
