<template>
  <div>
    考试
    <br>
    <button>{{das}}</button>
    <br>
    <span>地区：</span>
    <select name="" id="">
      <option value=""></option>
    </select>
    <br>
    <span>用户名</span>
    <input type="text">
    <br>
    <span>年龄：</span>
    <input type="text">
    <br>
    <table>
        <thead>
          <tr>
            <th></th>
          </tr>
        </thead>
        
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      das:'锁定',
      
    }
  },
  methods:{

  },

}
</script>
<style>
  
</style>