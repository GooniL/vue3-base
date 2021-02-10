<template>
<div>
  <div class="header">
    header
  </div>
  <div id="sub-container">

  </div>
</div>
</template>

<script>
import { onMounted } from 'vue'
import { registerMicroApps, setDefaultMountApp, start } from 'qiankun';

export default {
  name: 'App',
  setup() {
    onMounted(() => {
      registerMicroApps([
        {
          name: 'vue3', // app name registered
          entry: '//localhost:3001',
          container: '#sub-container',
          activeRule: '/vue3',
        },
      ])
      setDefaultMountApp('/vue3')
      start()
    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
