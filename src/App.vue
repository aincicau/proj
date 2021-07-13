<template>
  <div>
    <Person v-for="person of persons" :key="person.first" :firstName="person.first" :lastName="person.last"/>
  </div>
</template>

<script>
import Person from './components/Person.vue'

export default {
  name: 'App',
  components: {
    Person
  },
  data(){
    return{
      persons: []
    }
  },
  async created(){
    const url = "https://randomuser.me/api/?results=5";
    try{
      const result = await fetch(url);
      const json = await result.json();

      for (const pers of json.results){
        this.persons.push({
          first: pers.name.first,
          last: pers.name.last
        });
      }
    }catch(e){
      console.error("Error:", e);
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
