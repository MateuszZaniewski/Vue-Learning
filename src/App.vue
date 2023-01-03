<template>
  <div>

  <h1>{{ header }}</h1>
  <ul>
    <li v-for='{id, label} in items' :key='id'>{{label}}</li>
    <li v-for='({id, label}, index) in items' :key="id">{{ index }} {{ id }}.{{ label }} </li>
  </ul>

  </div>
  
</template>

<script>


export default {
  name: 'App',
  data () {
    return {
      header: 'Shopping lista',
      items : [
        {id: 1, label: 'kielbasa'},
        {id: 2, label: 'keczup'},
        {id: 3, label: 'majonez'}
      ]
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
