<template>
  <div>
    <h2>考试</h2>  
      <div class="left">
        <input type="text" v-model="ke">
      </div>
      <div class="right">

      </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      
    }
  },
}
</script>
<style >
    .left{
    width: 800px;
      height: 500px;
      background: #ccc;
      float: left;
  }
  .right{
    width: 800px;
    height: 500px;
    background: rgba(0, 0, 0, .8);
    float: left;
  }
</style>