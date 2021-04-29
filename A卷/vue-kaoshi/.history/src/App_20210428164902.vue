<template>
  <div>
    考试
    <br>
    <button @click="suo">{{das}}</button>
    <br>
    <span>地区：</span>
    <select v-model="ss">
      <option :value="item.name" v-for="(item, index) in list" :disabled="isT" :key="index" >
          {{item.name}}
      </option>
    </select>
    <br>
    <span>用户名</span>
    <input type="text" v-model="username" :disabled="isT">
    <br>
    <span>年龄：</span>
    <input type="number" v-model="age" :disabled="isT">
    <br>
    <button @click="abb" v-if="isShow" :disabled="isT">登录</button>
    <button  v-else @click="xiu" :disabled="isT"> 修改</button>
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
              <input type="checkbox" :value="index" v-model="checked" :disabled="isT">
            </td>
            <td>{{item.id}}</td>
            <td>{{item.username}}</td>
            <td>{{item.age}}</td>
            <td>{{item.ss}}</td>
            <td>
              <button @click="gai(index)" :disabled="isT"> 修改</button>
              <button @click="del(index)" :disabled="isT">删除</button>
            </td>
          </tr>
        </tbody>
        
    </table>
    <br>
    <br>
    <br>
    <div>
      <button @click="xuan" :disabled="isT">选中修改</button>
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
      nums:4,
      userIndex:'',
      checked:[],
      isT:false,
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
        this.userIndex = index
    },
    xiu(){
      console.log(this.goods[this.userIndex]);
      this.goods[this.userIndex].username = this.username
      this.goods[this.userIndex].age =  this.age
      this.goods[this.userIndex].ss = this.ss
      this.isShow = true
    },
    xuan(){
        this.checked.sort((a,b) =>{
            return b -a 
        }).forEach(item =>{
            this.goods.splice(item,1)
        })
        this.checked = []
    },
    suo(){
   
        if (this.das == '锁定') {
            var timer = setTimeout(()=>{
              this.num--
              this.das = this.num + '秒后解锁'
              this.isT = true
              if (this.num == 0) {
                clearTimeout(timer)
                this.das = '解锁'
               
                this.num = 3
              }
            },1000)
        }else{
          this.isT = false
        }

  },
  
  }
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