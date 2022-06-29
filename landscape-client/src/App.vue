<template>
  <div id='app'>
  <UserComponent v-bind:user="user" />
  <LandscapeComponent v-bind:landscapes="landscapes" />
  </div>

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import LandscapeComponent from './components/LandscapeComponent.vue'
import UserComponent from './components/UserComponent.vue'

import axios from 'axios';

export default {
  name: 'App',
  components: {
    LandscapeComponent,
    UserComponent
  },
  data: () => ({
    
      landscapes: {},
      user: {},
    
  }),
  mounted(){
    axios.get('http://127.0.0.1:8001/api/user')
    .then((response) => {
    this.user = response.data[0]
    console.warn("user",this.user)
    })

    
    axios.get('http://127.0.0.1:8001/api/album')
    .then((response) => {
    this.landscapes = response.data
    console.warn("ahahaha",this.landscapes)
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

