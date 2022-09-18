<template>
  <div id="app">
    <!--<Home/>-->
    <User/>
  </div>
</template>

<script>
import Home from './components/Home.vue'
import User from './components/User.vue'
import UserList from './components/UserList.vue'

export default {
  name: 'App',
  components: {
    User,
    UserList
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
