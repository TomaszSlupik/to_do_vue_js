<template>
  <div class="hello">
    <h2>Alert na kliknięcie</h2>
    <button @click="clickMe">Kliknij</button>
    <h1>{{ msg }}</h1>  

    <h2>Zadanie, które zostanie dodane:</h2>
    <h3>Zadanie => {{ newItem }}</h3>
    <input 
    class="todo"
    type="text" placeholder="zadanie"
    v-model="newItem"
    >
    
    <button
    @click="addItems"
    >Dodaj</button>

      <div 
      class="todoitem"
      v-for="item in items"
      :key="item.id"
      >
        {{ item.title }}
        <svg 
        @click="deleteItem(item.id)"
        xmlns="http://www.w3.org/2000/svg" width="22" height="22" fill="currentColor" class="bi bi-trash" viewBox="0 0 16 16">
        <path d="M5.5 5.5A.5.5 0 0 1 6 6v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5m2.5 0a.5.5 0 0 1 .5.5v6a.5.5 0 0 1-1 0V6a.5.5 0 0 1 .5-.5m3 .5a.5.5 0 0 0-1 0v6a.5.5 0 0 0 1 0z"/>
        <path d="M14.5 3a1 1 0 0 1-1 1H13v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V4h-.5a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1H6a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1h3.5a1 1 0 0 1 1 1zM4.118 4 4 4.059V13a1 1 0 0 0 1 1h6a1 1 0 0 0 1-1V4.059L11.882 4zM2.5 3h11V2h-11z"/>
      </svg>
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
      this.newItem = ""
    },
    deleteItem (id) {
      const index = this.items.findIndex(item => item.id === id) 
      if (index !== -1) {
        this.items.splice(index, 1);
      }
    }
  },
  // Moja lista zakupów
  data () {
    return {
      newItem: '',
      items: [
          {id: 0, title: 'zrobić zakupy'},
          {id: 1, title: 'pójśc do sklepu'},
      ]
    }
  }
  
}
</script>

<style>
button {
  width: 120px;
  height: 40px;
  border-radius: 10px;
  cursor: pointer;
}

input {
  height: 40px;
}

.todo {
  margin-right: 0.3em;
}

.todoitem {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.bi-trash {
  color: red;
}

svg {
  cursor: pointer;
}

</style>

