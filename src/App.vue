<template>
  <div>
    <h1>{{ header }}</h1>
    <!-- Podwójne {{ variable }} onazczają wyrażenie js, które ma zostać wyświetlone w template.
    Musi to być pojedyńcze wyrażenie, które zwraca jedną wartość. Można używać skrótów logicznych typu :
    {{ var || 'Hello' }} lub {{ var ? 'Hello' : 'Bye' }}-->

  <ul>
    <li v-for='{id, label} in items' :key='id'>{{label}}</li>
    <li v-for='({id, label}, index) in items' :key="id">{{ index }} {{ id }}.{{ label }} </li>
  </ul>
  <!-- Tak powstaje dynamicznie generowana lista, która składa się z eksportowanych elementów z sekcji <script>.
      Aby iterować po elementach tablicy lub obiektu, należy posłużyć się dyrektywą v-for='item in items' :key:'item'. Dodanie atrybutu :key nie jest wymagane ale jest dobrą praktyką przy dużych aplikacjach-->

  <input v-model.lazy="newItem" type="text" placeholder="Add an item">
    <ul>
      {{ newItem }}
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
      ],
      newItem: '',
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

<!-- Comment -->