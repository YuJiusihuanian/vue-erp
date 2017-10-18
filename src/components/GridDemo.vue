/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="GridDemo">
    <el-table
      :data="tableData"
      border
      stripe
      @row-dblclick="rowDblclick"
      @row-click="rowClick"
      @setCurrentRow
      highlight-current-row
      height="350"
      style="width: 100%;">
      <el-table-column
        fixed
        type="index"
        width="50">
      </el-table-column>
      <!--<el-table-column-->
        <!--label="日期"-->
        <!--sortable-->
        <!--width="180">-->
        <!--<template scope="scope">-->
          <!--<span v-if="alter" style="margin-left: 10px">{{ scope.row.date }}</span>-->
          <!--<el-input v-else v-model="scope.row.date" @blur="addRow(scope.$index, scope.store.states.data.length)"></el-input>-->
        <!--</template>-->
      <!--</el-table-column>-->
      <!--<el-table-column-->
        <!--label="姓名"-->
        <!--sortable-->
        <!--width="180">-->
        <!--<template scope="scope">-->
            <!--<span v-if="alter">{{ scope.row.name  }}</span>-->
            <!--<el-input v-else v-model="scope.row.name" @blur="addRow(scope.$index, scope.store.states.data.length)"></el-input>-->
        <!--</template>-->
      <!--</el-table-column>-->
      <!--<el-table-column label="地址" sortable>-->
        <!--<template scope="scope">-->
          <!--<span v-if="alter">{{ scope.row.address  }}</span>-->
          <!--<el-input v-else v-model="scope.row.address" @blur="addRow(scope.$index, scope.store.states.data.length)"></el-input>-->
        <!--</template>-->
      <!--</el-table-column>-->
      <el-table-column v-for='item in title' :prop="item" :label="item" :key='item'>
        <template scope="scope">
          <span v-if="alter" style="margin-left: 10px">{{ scope.row }}</span>
          <el-input v-else v-model="scope.column.label" @blur="addRow(scope.$index, scope.store.states.data.length, scope)"></el-input>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
  export default {
    props: ['alter', 'tableData', 'thisarow', 'title'],
    data () {
      return {
      }
    },
    methods: {
      addRow (row, rowN, scope) {
        console.log(row);
        console.log(scope);
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
            address: '',
            a: '',
            b: '',
            c: '',
            d: '',
            e: '',
            f: '',
            g: '',
            h: ''
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
      },
      rowClick (row, event, column){
//        this.$refs.singleTable.setCurrentRow(row);
      },
      rowDblclick (row,boole){
        console.log("第"+row.id+"行")
      }
    },
    mounted () {
    },
    watch: {

    }
  }
</script>
