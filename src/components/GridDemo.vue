<template>
  <div id="GridDemo">
    <el-button @click="clickAlter()" type="primary" icon="edit">修改</el-button>
    <el-button @click="add()" type="primary" icon="edit">新增一行</el-button>
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
        input:"",
        alter:true
      }
    },
    methods: {
      clickAlter(){
        this.alter = !this.alter;
        console.log(this.tableData);
      },
      add(){
          var a ={
              data:'',
              name:'',
              address:''
          }
          this.tableData.push(a);
      }
    }
  }
</script>
