<template>
    <todo-add 
    @addNewTodo="addNewTodo">
    </todo-add>
<todo-list
v-for="elem in data" 
        :title="elem.title" 
        :key="elem.id"
        :id="elem.id"
        :completed="elem.completed"
        @deleteById="deleteById"
        @changeColor="changeColor"
></todo-list>
</template>

<script>

import TodoList from './components/TodoList.vue'
import TodoAdd from './components/TodoAdd.vue'
export default{
components: {
        TodoList, TodoAdd
    },
    data(){
        return{
            data: [
                {id: 1, title: 'Позавтракать', completed: true},
                {id: 2, title: 'Почистить огурцы', completed: false},
                {id: 3, title: 'Помыть кота', completed: true},
            ]
        }
    },
    methods: {
        deleteById(id){
            this.data = this.data.filter(elem => elem.id !== id)
        },
        changeColor(id){
            const item = this.data.find((elem) => elem.id === id)
            item.completed = !item.completed
        },
        addNewTodo(newTodo){
        this.data.push(newTodo)
        }
    }
}
</script>

<style scoped>

</style>