/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="Index">
    <but v-on:clickAlter = "clickAlter" class="mod" text="修改" icon="edit"></but>
    <grid-demo :alter=alter :tableData=tableData></grid-demo>
  </div>
</template>
<script>
  import GridDemo from '../../components/GridDemo.vue'
  import Alter from '../../components/Alter.vue'
  import But from '../../components/Button.vue'
  export default{
    name: 'Index',
    data () {
      return {
        alter: true,
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
        aa: this.tableData,
      }
    },
    components: {
      GridDemo,
      Alter,
      But
    },
    methods: {
      clickAlter () {
        this.alter = !this.alter
        console.log(this.tableData)
      }
    },
    watch: {
      'ccc': function (val,oldval) {
          console.log(val)
          console.log(oldval)
      },
      tableData : {
        handler: function (val, oldVal) {
          this.aa = this.tableData[this.tableData.length - 1]
          console.log(this.aa)
        },
        deep: true
      },
//      aa : {
//        handler: function (val, oldVal) {
//          this.tableData.push({
//            data: '',
//            name: '',
//            address: ''
//          })
//        },
//        deep: true
//      }
    }
  }

</script>
<style>
  #Index .mod{
    margin-bottom:10px;
  }
</style>
