<template>
  <div id="app">
    <AddToDo v-on:add-Todo="addItemToList" />
    <Todos v-bind:todos="todos" v-on:todo-del="deletee" />
    <!-- name of file and this is one component -->
    <!-- vbind bind karega todo ko jo app ka data hai todos component se -->
  </div>

</template>

<script>

import Todos from './components/Todos'
import AddToDo from './components/AddTodo'

// to import the component file

export default {
  name: 'app',
  components: {
    Todos,
    AddToDo
  },
  data(){
    return{
      todos:[
        {
          id:1,
          title:'first',
          completed: false
        },
        {
          id:2,
          title:'second',
          completed: true
        },
        {
          id:3,
          title:'third',
          completed: false
        }
      ]
    }
  },
  methods:{
    deletee(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
      console.log(id)
    // todos me filter karo ki jo bhi id hai return hui uss id ke alava sab display hojaaye
    },
    addItemToList(newElement){
      this.todos = [...this.todos, newElement];
    }

  }
}
</script>

<style>

</style>
