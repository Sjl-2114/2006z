<template>
  <div>
    考试
    <br>
    <button>{{das}}</button>
    <br>
    <span>地区：</span>
    <select >
      <option :value="item.name" v-for="(item, index) in list" :key="index">
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
    <button @click="abb">登录</button>
    <button @click="abb">修改</button>
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
          <tr v-for="(item, index) in items" :key="index">
            <td>
              <input type="checkbox">
            </td>
            <td>332</td>
            <td>2343</td>
            <td>324423</td>
            <td>324423</td>
            <td>
              <button>修改</button>
              <button>删除</button>
            </td>
          </tr>
        </tbody>
        
    </table>
  </div>
</template>
<script>
  import data from '../public/data.json'
export default {
  data() {
    return {
      das:'锁定',
      list: data.data,
      usename:'',
      age:'',

    }
  },
  methods:{

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