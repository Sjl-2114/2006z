<template>
  <div>
    <h2>考试</h2>  
      <div class="left">
         <span>用户名：</span><input type="text" v-model="ke">
         <span style="color:red" v-show="isS">{{ndm}}</span>
        <br>
          <button @click="login">登录</button>
      </div>
      <div class="right" >
        asdf 
        <div class="ss" v-show="it">

        </div>
      </div>
  </div>
</template>
<script>
  import data from '../public/data.json'
export default {
  data() {
    return {
      ke:'',
      ndm:'请输入6~18位字符',
      isS:false,
      it:false,
    }
  },
  methods:{
    login(){
      let op = /^\w{6,18}$/
      let tt = op.test(this.ke)
      if (!tt) {
        this.isS = true
      } else {
         
      }
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
    
    float: left;
  }
  .ss{
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, .8);
    float: left;
  }
</style>