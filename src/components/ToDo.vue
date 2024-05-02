<template>
  <div class="hello">
    <h1>{{ msg }}</h1>  
    <button @click="clickMe">Kliknij</button>
      <div 
      v-for="item in items"
      :key="item.id"
      >
        {{ item.title }}
      </div>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  props: {
    msg: String
  },
  // Metoda na kliknięcie
  methods: {
    clickMe () {
      alert('Kliknięto w przcisk')
    }
  },
  // Moja lista zakupów
  data () {
    return {
      items: [
          {id: 0, title: 'zrobić zakupy'},
          {id: 1, title: 'pójśc do sklepu'},
      ]
    }
  }
  
}
</script>


<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
