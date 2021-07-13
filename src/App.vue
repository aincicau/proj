<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <ul>
    <li v-for="person of persons" :key="person.firstName">
      {{person.first}}
    </li>
  </ul>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
//import Person from './components/Person.vue'



export default {
  name: 'App',
  components: {
    HelloWorld//,
    //Person
  },
  data(){
    return{
      persons: [{
        first: "Maria",
        last: "Pop"
      },{
        first: "Adrian",
        last: "Mihalcea"
      }]
    }
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
