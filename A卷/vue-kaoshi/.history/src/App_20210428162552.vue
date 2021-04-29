<template>
  <div>
    考试
    <br>
    <button>{{das}}</button>
    <br>
    <span>地区：</span>
    <select v-model="ss">
      <option :value="item.name" v-for="(item, index) in list" :key="index" >
          {{item.name}}
      </option>
    </select>
    <br>
    <span>用户名</span>
    <input type="text" v-model="username">
    <br>
    <span>年龄：</span>
    <input type="number" v-model="age">
    <br>
    <button @click="abb" v-if="isShow">登录</button>
    <button  v-else @click="xiu"> 修改</button>
    <br>
    <table style="width:100%" class="table">
        <thead>
          <tr>
            <th></th>
            <th>ID</th>
            <th>姓名</th>
            <th>年龄</th>
            <th>地区</th>
            <th>操作</th>
           
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in goods" :key="index">
            <td>
              <input type="checkbox">
            </td>
            <td>{{item.id}}</td>
            <td>{{item.username}}</td>
            <td>{{item.age}}</td>
            <td>{{item.ss}}</td>
            <td>
              <button @click="gai(index)">修改</button>
              <button @click="del(index)">删除</button>
            </td>
          </tr>
        </tbody>
        
    </table>
    <br>
    <br>
    <br>
    <div>
      <button @click="xuan(index)">选中修改</button>
    </div>
  </div>
</template>
<script>
  import data from '../public/data.json'
export default {
  data() {
    return {
      das:'锁定',
      list: data.data,
      username:'',
      age:'',
      isShow:true,
      goods:[],
      num:1,
      ss:'',
      userIndex
    }
  },
  methods:{
    abb(){
        let obj = {
          username :this.username,
          age:this.age,
          isShow:this.isShow,
          id:this.num++,
          ss:this.ss
        }
        
        this.goods.push(obj)
    },
    del(index){
        this.goods.splice(index,1)
    },
    gai(index){
      let data = this.goods[index];

        this.isShow = false
        this.username = data.username
        this.age = data.age
        this.ss = data.ss

    },
    xiu(){
     
     
    }

  },

}
</script>
<style>
  .table{
    text-align: center;
    border: 1px solid red;
  }
  thead{
    background: #ccc;
  }
  td{
    border: 1px solid #ccc;
  }
</style>