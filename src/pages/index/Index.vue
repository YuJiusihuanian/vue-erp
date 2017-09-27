<template>
  <div id="Index">
    <grid-demo></grid-demo>
  </div>
</template>
<script>
  import GridDemo from '../../components/GridDemo.vue';
  import Alter from '../../components/Alter.vue';
  export default{
    name:"Index",
    date(){
      return{

      }
    },
    components:{
      GridDemo,
      Alter
    }
  }

</script>
<style>
  #Index .hello{
    margin-bottom:10px;
  }
</style>
