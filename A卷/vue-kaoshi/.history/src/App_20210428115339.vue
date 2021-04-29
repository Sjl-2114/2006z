<template>
  <div>
    考试
    <select name="" id="">
      <option value=""></option>
    </select>
    <br>
    <span>用户名</span>
    //axios设置请求拦截器
    axios.interceptors.request.use(config => {
      config.headers.mytoken = 'nihao' //设置响应头
      return config
    }, err => {
      console.log(err)
    })

    <input type="text">
  </div>
</template>