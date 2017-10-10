/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="GridDemo">
    <el-table
      :data="tableData"
      border
      stripe
      style="width: 100%">
      <el-table-column
        label="日期"
        width="180">
        <template scope="scope">
          <span v-if="alter" style="margin-left: 10px">{{ scope.row.date }}</span>
          <el-input v-else v-model="scope.row.date" @blur="addRow(scope.$index, scope.store.states.data.length)"></el-input>
        </template>
      </el-table-column>
      <el-table-column
        label="姓名"
        width="180">
        <template scope="scope">
            <span v-if="alter">{{ scope.row.name  }}</span>
            <el-input v-else v-model="scope.row.name" @blur="addRow(scope.$index, scope.store.states.data.length)"></el-input>
        </template>
      </el-table-column>
      <el-table-column label="地址">
        <template scope="scope">
          <span v-if="alter">{{ scope.row.address  }}</span>
          <el-input v-else v-model="scope.row.address" @blur="addRow(scope.$index, scope.store.states.data.length)"></el-input>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
  export default {
    props: ['alter', 'tableData', 'thisarow'],
    data () {
      return {
      }
    },
    methods: {
      addRow (row, rowN) {
        //console.log(row);
        //console.log(rowN);
        if (this.tableData[this.tableData.length - 1].date == '' &&
          this.tableData[this.tableData.length - 1].name == '' &&
          this.tableData[this.tableData.length - 1].address == '' ) return;
        this.$emit('addRow');
        this.tableData.forEach(function(a){
            //console.log(a);
        })
        for (var filed in this.tableData){
          //console.log(filed.name);
        }
        if (row + 1 == rowN) {
          this.tableData.push({
            date: '',
            name: '',
            address: ''
          })
        }
        var attributeCount = function(obj) {
          var count = 0;
          for (var i in obj) {
            if (obj.hasOwnProperty(i)) {  // 建议加上判断,如果没有扩展对象属性可以不加
              count++;
            }
          }
          return count;
        }
        console.log(attributeCount(this.tableData[0]))
      }
    },
    mounted () {

    },
    watch: {

    }
  }
</script>
