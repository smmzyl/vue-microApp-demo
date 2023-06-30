<template>
  <div id="app">
    <h1>我是子程序 --- 开头</h1>
    <img src="./assets/logo.png">
    <h1>我是子程序 --- 结尾</h1>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
}
const data = window.microApp.getData() // 返回基座下发的data数据
console.info(data)
window.microApp.setGlobalData({type: '全局数据'})
if (window.__MICRO_APP_ENVIRONMENT__) {
  console.log('我在微前端环境中')
  window.microApp.removeDomScope()
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
