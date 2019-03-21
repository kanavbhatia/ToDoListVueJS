<template>
    <div>
    <div class="lol" v-bind:class="{'is-completed':todo.completed}">
        <p> 
            <input type="checkbox" v-on:change="markCompleted">
            {{todo.title}}
            <button v-on:click="$emit('todo-del',todo.id)">x</button>
        </p>
        <!-- jo bhi completed true hoga un par properties lag jayegi -->
        <!-- v-bind:key dena hota hai because each component ko ek unique id deni hoti hai -->
    </div>
    </div>
</template>
 
<script>
export default {
    name: 'Todoitem',
    methods:{
        markCompleted(){
            this.todo.completed = !this.todo.completed
        }
    },
    props: ['todo']
}
</script>

<style scoped>
    .is-completed{
        text-decoration: line-through;
    }

    .lol{
        background-color: aquamarine;
    }
</style>


