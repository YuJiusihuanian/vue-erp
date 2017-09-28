/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="Index">
    <but @clickMethod="clickAlter" class="mod" text="修改" icon="edit" :disabled="disabled"></but>
    <but @clickMethod="save" class="mod" text="保存" icon="check":disabled="!disabled"></but>
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
        disabled: false
      }
    },
    components: {
      GridDemo,
      Alter,
      But
    },
    methods: {
      clickAlter () {
        this.disabled = !this.disabled
        if (this.alter == true){
          this.tableData.push({
            date: '',
            name: '',
            address: ''
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
      }
    },
    watch: {

    }
  }

</script>
<style>
  #Index .mod{
    margin-bottom:10px;
    width:10%;
    float:left;
  }
</style>
