/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="GridDemo">
    <el-table
      :data="tableData"
      border
      style="width: 100%">
      <el-table-column
        label="日期"
        width="180">
        <template scope="scope">
          <span v-if="alter" style="margin-left: 10px">{{ scope.row.date }}</span>
          <el-input v-else v-model="scope.row.date"></el-input>
        </template>
      </el-table-column>
      <el-table-column
        label="姓名"
        width="180">
        <template scope="scope">
            <span v-if="alter">{{ scope.row.name  }}</span>
            <el-input v-else v-model="scope.row.name"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="地址">
        <template scope="scope">
          <span v-if="alter">{{ scope.row.address  }}</span>
          <el-input v-else v-model="scope.row.address"></el-input>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
  export default {
    props: ['alter', 'tableData'],
    data () {
      return {
        input: '',
      }
    },
    methods: {
      add () {
        var a ={
          data: '',
          name: '',
          address: ''
        }
        this.tableData.push(a)
      }
    },
    mounted () {
//      console.log(this.tableData[this.tableData.length - 1])
//      this.tableData.push({
//        date: '',
//        name: '',
//        address: ''
//      })
//      console.log(this.tableData[this.tableData.length - 1])
    },
    watch: {
      'input' (val, oldval) {
        console.log(val);
        console.log(oldval);
//        deep: true
//        console.log(val)
//        console.log(oldval)
//        let check = this.tableData[this.tableData.length - 1];
//        console.log(check);
//        if (check.data != this.tableData[this.tableData.length - 1].data || check.name != this.tableData[this.tableData.length - 1].name ||
//          check.address != this.tableData[this.tableData.length - 1].address) {
//          this.tableData.push({
//            date: '',
//            name: '',
//            address: ''
//          })
//        }
      }
    }
  }
</script>
