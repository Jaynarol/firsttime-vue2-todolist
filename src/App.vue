<template>
  <div id="app">
    <h1>To-Do List</h1>
    <new-todo @handleNewItem="addNewItem"></new-todo>
    <todo-list :items="items" @handleRemoveItem="removeItem"></todo-list>
  </div>
</template>

<script>
  import NewTodo from './components/NewTodo'
  import TodoList from './components/TodoList'

  let items = [{id: 1, name: "first", completed: false}];

  export default {
    name: 'app',
    data(){
      return {
        items
      }
    },
    methods: {
      addNewItem: function(newitem) {
        if ( !newitem ) {
          return
        }
        items.push({id: (items.slice(-1)[0] || {id: 0}).id + 1, name: newitem, completed: false})
      },
      removeItem: function(itemid) {
        items.splice(items.findIndex((item)=>item.id == itemid), 1)
      }
    },
    components: {
      NewTodo, TodoList
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    display: table;
    margin: 0 auto;
  }
</style>
