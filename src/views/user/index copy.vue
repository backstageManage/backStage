<template>
  <div class="user-yr">
    <el-row class="search-row">
      <span>搜索输入</span>
      <el-input v-model="search.keyword" placeholder="请输入用户ID/编号" class="mlr10" />
      <span>收货人</span>
      <el-input v-model="search.userName" placeholder="请输入用户昵称" class="mlr10" />
      <el-button type="primary">查询</el-button>
    </el-row>

    <el-table
      :data="tableData"
      border
      styel="width: 100%"
      class="mb20"
    >
      <template v-for="(item, index) in tableMap">
        <el-table-column
          :key="index"
          :prop="item.prop"
          :label="item.label"
          :width="item.width"
          align="center"
        >
          <template slot-scope="{row}">
            <span v-if="item.prop === 'deal'" class="can-click c-main-blue">
              <i class="el-icon-search" /> 查看
            </span>
            <div v-else-if="item.prop === 'consumption'">
              ￥{{ row[item.prop] }}
            </div>
            <div v-else>{{ row[item.prop] }}</div>
          </template>
        </el-table-column>
      </template>
    </el-table>

    <el-pagination
      :current-page="search.currentPage"
      :page-size="search.pageSize"
      layout="pager, total, prev, next, jumper"
      :total="total"
      prev-text="上一页"
      next-text="下一页"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: {
        keyword: '',
        name: '',
        currentPage: 1,
        pageSize: 10
      },
      total: 0,
      tableMap: [
        { label: '编号', prop: 'no' },
        { label: '用户ID', prop: 'userId', width: '250' },
        { label: '用户昵称', prop: 'userName' },
        { label: '用户账号', prop: 'userCount' },
        { label: '订单数量', prop: 'orderNumber' },
        { label: '消费金额', prop: 'consumption' },
        { label: '可用金币', prop: 'availMoney' },
        { label: '操作', prop: 'deal' }
      ],
      tableData: [
        { no: '10001', userId: '2019053129549843211', userName: '小猫咪', userCount: '13801020156', orderNumber: '20', consumption: '2800.00', availMoney: '10000' }
      ]
    }
  },
  methods: {
    handleSizeChange(val) {
      console.log(`每页 ${val} 条`)
    },
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`)
    }
  }
}
</script>
