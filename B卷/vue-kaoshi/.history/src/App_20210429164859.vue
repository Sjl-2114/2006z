<template>
  <div>
    <h2>考试</h2>  
      <div class="left">
         <span>用户名：</span><input type="text" v-model="ke">
        <br>
          <button @click="login">登录</button>
      </div>
      <div class="right">

      </div>
  </div>
</template>
<script>
  import data from '../public/data.json'
export default {
  data() {
    return {
      ke:'',
    }
  },
  methods:{
    login(){
      let op = /^\w{6,18}$/
      let tt = op.test()
    }
  }
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