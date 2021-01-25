<template>
  <div class="table_wrap">
    <el-table
      :data="tableData"
      :header-row-style="{background: '#13a3f1'}"
      :header-cell-style="{background: '#13a3f1', color: '#fff'}"
      style="width: 100%;text-align: center">
      <el-table-column
        label="起始/中转/目的"
        >
        <template slot-scope="scope">
          <div class="distance_wrap">
            <p class="add_tag1">{{ scope.row.departure }}</p>
            <p style="color: #a2a2a2;font-size: 10px"><i class="el-icon-warning" style="color: #13a3f1"></i>{{ scope.row.transfer }}</p>
            <p class="add_tag2">{{ scope.row.arrive }}</p>
          </div>
        </template>
      </el-table-column>
      <el-table-column
        label="20GP"
        align="center"
        width="180">
        <template slot-scope="scope">
          <span style="color: red;">{{ `$${ scope.row.price1 }` }}</span>
        </template>
      </el-table-column>
      <el-table-column
        label="40GP"
        align="center"
        width="180">
        <template slot-scope="scope">
          <span style="color: red;">{{ `$${ scope.row.price2 }` }}</span>
        </template>
      </el-table-column>
      <el-table-column
        label="40HQ"
        align="center"
        width="180">
        <template slot-scope="scope">
          <span style="color: red;">{{ `$${ scope.row.price3 }` }}</span>
        </template>
      </el-table-column>
      <el-table-column
        label="船期"
        align="center"
        width="220">
        <template slot-scope="scope">
          <span>{{ scope.row.date }}</span>
          <p v-if="scope.row.tip" style="color: #a2a2a2;font-size: 12px">{{ scope.row.tip }}</p>
        </template>
      </el-table-column>
      <el-table-column
        label=""
        align="center"
        width="180">
        <template slot-scope="scope">
          <el-button type="primary" @click="open(scope.row)">咨询</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
  </template>

<script>
  export default {
    layout: 'banner',
    head() {
      return {
        title: '运费查询'
      }
    },
    data() {
      return {
        tableData: [
          {
            date: '周二',
            tip: '内陆点单票价格',
            transfer: '直达',
            departure: '上海',
            arrive: '北京',
            price1: 669,
            price2: 1269,
            price3: 1369
          },
          {
            date: '周二',
            transfer: '直达',
            departure: '上海',
            arrive: '北京',
            price1: 669,
            price2: 1269,
            price3: 1369
          },
          {
            date: '周二',
            transfer: '直达',
            departure: '上海',
            arrive: '北京',
            price1: 669,
            price2: 1269,
            price3: 1369
          },
          {
            date: '周二',
            tip: '内陆点单票价格',
            transfer: '直达',
            departure: '上海',
            arrive: '北京',
            price1: 669,
            price2: 1269,
            price3: 1369
          },
          {
            date: '周二',
            transfer: '直达',
            departure: '上海',
            arrive: '北京',
            price1: 669,
            price2: 1269,
            price3: 1369
          },
          {
            date: '周二',
            transfer: '直达',
            departure: '上海',
            arrive: '北京',
            price1: 669,
            price2: 1269,
            price3: 1369
          }
        ]
      }
    },
    methods: {
      open(data) {
        this.$alert(`${ data.price1 }`, '运费', {
          confirmButtonText: '确定'
        });
      }
    }
  }
</script>

<style>
  .table_wrap {
    width: calc(100% - 100px);
    margin: 0 auto;
  }
  .distance_wrap{
    padding-left: 20px;
    display: flex;
    flex-direction: column;
  }
  .distance_wrap::before{
    display: block;
    content: '';
    height: 52px;
    border-left: 1px solid #13a3f1;
    position: absolute;
    top: 20px;
    left: 10px;
  }
  .distance_wrap .el-icon-warning{
    position: absolute;
    left: 3px;
    top: 41px;
    font-size: 14px;
  }
  .distance_wrap .add_tag1::before{
    display: block;
    content: '';
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: #13a3f1;
    position: absolute;
    top: 20px;
    left: 7px;
  }
  .distance_wrap .add_tag2::before{
    display: block;
    content: '';
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: #13a3f1;
    position: absolute;
    top: 68px;
    left: 7px;
  }
</style>