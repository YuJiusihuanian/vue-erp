/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="Button">
    <el-button @click="clickAlter" type="primary" :icon="icon">{{text}}</el-button>
  </div>
</template>
<script>
    export default{
      name: 'Button',
      props: ['text', 'icon'],
      data () {
        return {
        }
      },
      methods: {
        clickAlter () {
          this.$emit('clickAlter');
        }
      }
    }
</script>
<style scoped>
</style>
