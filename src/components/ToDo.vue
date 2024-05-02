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

