<template>
  <div>
    <el-table
        :data="tableData"
        height="250"
        border
        @selection-change="handleSelectionChange"
        style="width: 100%">
      <el-table-column
          type="selection"
          align="center"
          width="55">
      </el-table-column>

      <el-table-column
          prop="date"
          label="日期"
          align="center"
          width="180">
      </el-table-column>

      <el-table-column
          prop="name"
          label="姓名"
          align="center"
          width="180">
      </el-table-column>

      <el-table-column
          prop="address"
          align="center"
          label="地址">
      </el-table-column>

    </el-table>
  </div>
</template>

<script>
import Vue from 'vue';
import {Table, TableColumn} from 'element-ui';

Vue.use(Table);
Vue.use(TableColumn);

export default {
  name: "test",
  data() {
    return {
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }],
      dateNew: '',
      nameNew: '',
      addressNew: ''

    }
  },
  methods: {
    handleSelectionChange(row) {
      let oeInfoSelection = {
        oeInfo: row.map(item => ({
          oeIdNew:item.date,
          oeNameNew:item.name,
          oeCodeNew:item.address
        }))
      };

      /*
        let outsideEmterpeiseInfo = {
          oeInfo: oeInfoSelection.map(item => ({
            oeIDNEW:item.oeiId,
            oeCodeNEW:item.oeiCode,
            oeNameNEW:item.oeiName
          }))
        };
      */

      /*
      * 判断row.length与1的关系是不相等的.
      * 当第一次点击表格的选中框时, row.length !== 1是false, 因为现在选中的就是一行数据, row.length就是1. 而判断的row.length不是1, 所以输出false
      * */
      console.log("this.single -> ", row.length !== 1);
      console.log("<br>");
      /*
      * 判断row.length
      * 当第一次点击表格的选中框时, row.length !== 1是false, 因为现在选中的就是一行数据, row.length就是1. 而判断的row.length不是1, 所以输出false
      * */
      console.log("this.multiple -> ", !row.length);

      console.log("userNewsDate：", oeInfoSelection);
      console.log("测试");
    }
  }
}
</script>
<style scoped>

</style>
