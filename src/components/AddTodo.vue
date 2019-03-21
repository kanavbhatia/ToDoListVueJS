<template>
    <div>
        <form @submit="addFunc">
            <input type="text" v-model="title" placeholder="Add item..."> 
            <!-- what is v-model used for? -->
            <input type="submit" value="Submit"> 
        </form>
    </div>
</template>

<script>

import uuid from 'uuid'

export default {
    name: 'AddToDo',
    data(){
        return{
            title: ''
        }
    },
    methods:{
        addFunc(e){
            e.preventDefault()
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false   
            }
        //send it to the parent
        this.$emit('add-Todo',newTodo) 
        } 
        
    }
}
</script>

<style scoped>

</style>

