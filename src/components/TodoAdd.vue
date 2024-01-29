<template>
    <div>
      <h1>ToDo App</h1>
      <input type="text" v-model="newTodos.title" @keyup.enter="addNewTodo">
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTodos: [{
            id: Date.now(),
            title: '',
            completed: false
        }]
      }
    },
    methods: {
      addNewTodo() {
        
          this.$emit('addNewTodo', this.newTodos);
        
      }
    }
  }
  </script>
  