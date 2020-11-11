<template>
  <div>
    <el-row class="nav">
      <div class="input-suffix">
        输入检索：
        <el-input v-model="input1" size="·medium" placeholder="请输入用户ID/账号" />
      </div>
      <div class="input-suffix">
        收货人：
        <el-input v-model="input2" size="medium" placeholder="请输入用户昵称" />
      </div>
      <el-button type="primary">搜索</el-button>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input1: '',
      input2: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.nav{
  box-sizing: border-box;
  display: flex;
  align-items: center;
  color: #bbbbbb;
  .input-suffix {
    box-sizing: border-box;
    width: 300px;
    display: flex;
    align-items: center;
    font-size: 14px;
    justify-content: space-between;
    margin-right: 30px;
  }
  .el-input{
    width: 70%;
  }
}
</style>
