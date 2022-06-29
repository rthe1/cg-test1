<template>
  <div id='app'>
  <UserComponent v-bind:user="user" />
  <div class="landscape-container">
  <LandscapeComponent v-bind:landscapes="landscapes" />
  </div>
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
    axios.get('http://127.0.0.1:8000/api/user')
    .then((response) => {
    this.user = response.data[0]
    console.warn("user",this.user)
    })

    
    axios.get('http://127.0.0.1:8000/api/album')
    .then((response) => {
    this.landscapes = response.data
    console.warn("ahahaha",this.landscapes)
    })
    

  }
}
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.landscape-container{
   display: grid;
   justify-content: space-around;
    margin: 10px;
  padding: 10px;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3, 1fr);
  width: 70%;
  height: 400px;
}
</style>

