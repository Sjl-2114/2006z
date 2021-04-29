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
    <input type="text">
    <br>
    <span>年龄：</span>
    <input type="number">
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
        <tfoot></tfoot>
        
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

    }
  },
  methods:{

  },

}
</script>
<style>
  .table{
    background: #ccc;
  }
</style>