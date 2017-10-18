/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="Index">
    <but @clickMethod="clickAlter" class="mod" text="修改" icon="el-icon-edit" :disabled="disabled"></but>
    <but @clickMethod="save" class="mod" text="保存" icon="el-icon-check" :disabled="!disabled"></but>
    <grid-demo @addRow="addRow" :alter=alter :tableData=tableData :title=title></grid-demo>
    <hel></hel>
  </div>
</template>
<script>
  import GridDemo from '../../components/GridDemo.vue'
  import Alter from '../../components/Alter.vue'
  import But from '../../components/Button.vue'
  import Hel from '../../components/Hello.vue'
  export default{
    name: 'Index',
    data () {
      return {
        alter: true,
        tableData: [{
          id: '1',
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
          a: '上海市普陀区金沙江路 1518 弄',
          b: '上海市普陀区金沙江路 1518 弄',
          c: '上海市普陀区金沙江路 1518 弄',
          d: '上海市普陀区金沙江路 1518 弄',
          e: '上海市普陀区金沙江路 1518 弄',
          f: '上海市普陀区金沙江路 1518 弄',
          g: '上海市普陀区金沙江路 1518 弄',
          h: '上海市普陀区金沙江路 1518 弄'
        }, {
          id: '2',
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄',
          a: '上海市普陀区金沙江路 1518 弄',
          b: '上海市普陀区金沙江路 1518 弄',
          c: '上海市普陀区金沙江路 1518 弄',
          d: '上海市普陀区金沙江路 1518 弄',
          e: '上海市普陀区金沙江路 1518 弄',
          f: '上海市普陀区金沙江路 1518 弄',
          g: '上海市普陀区金沙江路 1518 弄',
          h: '上海市普陀区金沙江路 1518 弄'
        }, {
          id: '3',
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄',
          a: '上海市普陀区金沙江路 1518 弄',
          b: '上海市普陀区金沙江路 1518 弄',
          c: '上海市普陀区金沙江路 1518 弄',
          d: '上海市普陀区金沙江路 1518 弄',
          e: '上海市普陀区金沙江路 1518 弄',
          f: '上海市普陀区金沙江路 1518 弄',
          g: '上海市普陀区金沙江路 1518 弄',
          h: '上海市普陀区金沙江路 1518 弄'
        }, {
          id: '4',
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄',
          a: '上海市普陀区金沙江路 1518 弄',
          b: '上海市普陀区金沙江路 1518 弄',
          c: '上海市普陀区金沙江路 1518 弄',
          d: '上海市普陀区金沙江路 1518 弄',
          e: '上海市普陀区金沙江路 1518 弄',
          f: '上海市普陀区金沙江路 1518 弄',
          g: '上海市普陀区金沙江路 1518 弄',
          h: '上海市普陀区金沙江路 1518 弄'
        },{
          id: '4',
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄',
          a: '上海市普陀区金沙江路 1518 弄',
          b: '上海市普陀区金沙江路 1518 弄',
          c: '上海市普陀区金沙江路 1518 弄',
          d: '上海市普陀区金沙江路 1518 弄',
          e: '上海市普陀区金沙江路 1518 弄',
          f: '上海市普陀区金沙江路 1518 弄',
          g: '上海市普陀区金沙江路 1518 弄',
          h: '上海市普陀区金沙江路 1518 弄'
        },{
          id: '4',
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄',
          a: '上海市普陀区金沙江路 1518 弄',
          b: '上海市普陀区金沙江路 1518 弄',
          c: '上海市普陀区金沙江路 1518 弄',
          d: '上海市普陀区金沙江路 1518 弄',
          e: '上海市普陀区金沙江路 1518 弄',
          f: '上海市普陀区金沙江路 1518 弄',
          g: '上海市普陀区金沙江路 1518 弄',
          h: '上海市普陀区金沙江路 1518 弄'
        }
        ],
        title: ['date', 'name', 'address', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'],
        disabled: false
      }
    },
    components: {
      GridDemo,
      Alter,
      But,
      Hel
    },
    methods: {
      clickAlter () {
        this.disabled = !this.disabled
        if (this.alter == true){
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
        this.alter = false
      },
      save () {
        this.disabled = !this.disabled
        if (this.alter == false){
          this.tableData.pop()
        }
        this.alter = true
      },
      addRow (row, rowN) {


      }
    },
    watch: {

    }
  }

</script>
<style>
  #Index .mod{
    margin-bottom:10px;
  }
</style>
