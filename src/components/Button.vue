/**
* Created by fangweijun on 2017/9/27.
*/
<template>
  <div id="Button">
    <el-button @click="clickMethod" type="primary" :icon="icon" :disabled="disabled">{{text}}</el-button>
  </div>
</template>
<script>
    export default{
      name: 'Button',
      props: ['text', 'icon', 'disabled'],
      data () {
        return {
        }
      },
      methods: {
        clickMethod () {
          this.$emit('clickMethod');
        }
      }
    }
</script>
<style scoped>
  #Button{
    display:inline-block;
  }
</style>
