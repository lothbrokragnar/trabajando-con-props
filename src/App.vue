<template>
  <div id="app">
    <h1><u>Lista de Supermercado</u></h1>
    <form @submit.prevent="addNewListItem">
      <label>Tarea </label>
      <input placeholder="Ingresa nueva tarea" v-model="newListItem">
      <button type="submit">Añadir</button>
    </form>
    <list v-bind:listItems="listItems" @delete-item="deleteItem" @delete-list="deleteList"></list>
  </div>
</template>

<script>
  import List from './components/List.vue'

  export default {
    name: 'App',
    components: {
      List
    },
    data() {
      return {
        newListItem: '',
        listItems: [],
      }
    },
    methods: {
      addNewListItem() {
        const newItem = this.newListItem
        const list = this.listItems
        list.push(newItem)
      },
      deleteItem(index) {
        const list = this.listItems
        list.splice(index, 1)
      },
      deleteList(){
        this.listItems = []
      }
    },
  }
</script>

<style>
*{
  text-align: center;
}
li{
  margin: 10px 0;
}
</style>