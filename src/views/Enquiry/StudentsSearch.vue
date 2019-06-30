<template>
  <div>
    <el-card v-if="type" class="box-card search">
      <h2>学员id进行搜索</h2>
      <el-input v-model="input" class="space" size="medium" placeholder="请输入学员ID" />
      <el-button v-waves class="space" size="medium" type="primary" @click="sendSearch">搜索</el-button>
    </el-card>
    <el-card v-else class="box-card search">
      <h2>搜索学员ID失败，请先登录客户端绑定手机号</h2>
      <el-image
        style="width: 200px; height: 100px"
        :src="errGif"
        fit="contain"
      />
      <el-button v-waves class="space" type="primary" size="medium" @click="sendSearch">关闭</el-button>
    </el-card>
  </div>
</template>

<script>
import { fetchList } from '@/api/article'
import waves from '@/directive/waves/index.js'
import errGif from '@/assets/images/chaxunshibai.jpg'

export default {
  name: 'StudentsSearch',
  directives: {
    waves
  },
  data() {
    return {
      errGif: errGif,
      input: '',
      type: 'true'
    }
  },
  methods: {
    sendSearch() {
      console.log('搜索')
      console.log(this.input)
      fetchList({ 'id': this.input }).then(res => {
        console.log(res)
        this.type = !this.type
      })
    }
  }
}
</script>

<style>
  .search{
    width: 500px;
    height: 300px;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    text-align: center;
    border-radius: 25px;
  }
  .search .el-input__inner {
    border-radius: 0;
    border-top: 0;
    border-left: 0;
    border-right: 0;
  }
  .search .el-card__body {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
  }
  .space{
    width: 250px;
    display: block;
  }
</style>
