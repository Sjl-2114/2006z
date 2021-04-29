<template>
  <div>
    <h2>考试</h2>
    <div class="left">
      <span>用户名：</span><input type="text" v-model="ke" />
      <span style="color: red" v-show="isS">{{ ndm }}</span>
      <br />
      <button @click="login">登录</button>
    </div>
    <div class="right"  >
      <div class="ss" v-show="it"></div>
      <div v-for="(item, index) in list" :key="index" v-show="commIndex == index">

        <p>{{item.title}}</p>
        <div v-for="(item1, index1) in item.options" :key="index1">
            <input type="radio" :value="index" v-model="t1"> <span>{{item1}}</span><br>
        </div>
      </div>
     
    </div>
  </div>
</template>
<script>
import data from "../public/data.json";
export default {
  data() {
    return {
      ke: "",
      ndm: "请输入6~18位字符",
      isS: false,
      it: true,
      list:data.data,
      commIndex:0,
      t1:-1,
    };
  },
  methods: {
    login() {
      let op = /^\w{6,18}$/;
      let tt = op.test(this.ke);
      if (!tt) {
        this.isS = true;
      } else {
        this.it = false;
        alert("登陆成功");
      }
    },
  },
};
</script>
<style >
.left {
  width: 800px;
  height: 500px;
  background: #ccc;
  float: left;
}
.right {
  width: 800px;
  height: 500px;
  margin-left: 20px;
  background: #ccc;
  float: left;
  position: relative;
}
.ss {
  position: absolute;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  float: left;
}
</style>