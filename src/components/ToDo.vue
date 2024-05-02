<template>
  <div class="hello">
    <h2>Alert na kliknięcie</h2>
    <button @click="clickMe">Kliknij</button>
    <h1>{{ msg }}</h1>  

    <input type="text" placeholder="zadanie"
    v-model="newItem"
    >
    {{ newItem }}
    <button
    @click="addItems"
    >Dodaj</button>

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
    },
    addItems() {
      this.items.push({
        id: Math.random(),
        title: this.newItem
      })
    }
  },
  // Moja lista zakupów
  data () {
    return {
      newItem: 'default',
      items: [
          {id: 0, title: 'zrobić zakupy'},
          {id: 1, title: 'pójśc do sklepu'},
      ]
    }
  }
  
}
</script>

