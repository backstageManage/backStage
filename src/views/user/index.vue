<template>
  <div class="content">
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
    <el-table
      :data="list"
      border
      fit
      highlight-current-row
    >
      <el-table-column align="center" label="编号">
        <template slot-scope="scope">
          {{ scope.row.index }}
        </template>
      </el-table-column>
      <el-table-column label="用户ID" align="center">
        <template slot-scope="scope">
          {{ scope.row.id }}
        </template>
      </el-table-column>
      <el-table-column label="用户昵称" align="center">
        <template slot-scope="scope">
          <span>{{ scope.row.author }}</span>
        </template>
      </el-table-column>
      <el-table-column label="用户账号" align="center">
        <template slot-scope="scope">
          {{ scope.row.account }}
        </template>
      </el-table-column>
      <el-table-column label="订单数量" align="center">
        <template slot-scope="scope">
          {{ scope.row.number }}
        </template>
      </el-table-column>
      <el-table-column align="center" label="消费金额">
        <template slot-scope="scope">
          <span>¥{{ scope.row.money }}</span>
        </template>
      </el-table-column>
      <el-table-column align="center" label="可用金币">
        <template slot-scope="scope">
          <span>{{ scope.row.use }}</span>
        </template>
      </el-table-column>
      <el-table-column align="center" label="操作">
        <template>
          <i class="el-icon-edit-outline" />
          <span>查看</span>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input1: '',
      input2: '',
      list: [{
        index: '10001',
        id: '202011120920',
        author: '小肉肉',
        account: '15143563452',
        number: '13',
        money: '200.00',
        use: '500.00'
      },
      {
        index: '10002',
        id: '202011120920',
        author: '小肉肉',
        account: '15143563452',
        number: '13',
        money: '200.00',
        use: '500.00'
      },
      {
        index: '10003',
        id: '202011120920',
        author: '小肉肉',
        account: '15143563452',
        number: '13',
        money: '200.00',
        use: '500.00'
      }]
    }
  }
}
</script>

<style lang="scss" scoped>
.content{
  box-sizing: border-box;
  width: 100%;
  padding: 30px;
}
.nav{
  box-sizing: border-box;
  display: flex;
  align-items: center;
  color: #bbbbbb;
  margin-bottom: 30px;
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
.el-icon-time{
  color: greenyellow;
  margin-right: 5px;
}
</style>
