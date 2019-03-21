<template>
    <div>
        <!-- <h1>Todo</h1> -->
    <div v-for="todo in todos" v-bind:key="todo.id">
        <!-- <h3>{{todo.title}}</h3> -->
        <Todoitem v-bind:todo="todo" v-on:todo-del="$emit('todo-del',todo.id)"/>
        <!-- v-bind:key dena hota hai because each component ko ek unique id deni hoti hai -->
    </div>
    </div>
</template>
 
<script>
import Todoitem from './Todoitem';

export default {
    name: 'Todos',
    components: {
        Todoitem
  },
    props: ['todos']
}
</script>

<style scoped>
    
</style>


