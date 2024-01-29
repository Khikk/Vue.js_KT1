<template>
    <div class="wrapper">
      <div>
        <div
          class="todo_item"
          @dblclick="deleteById"
          @click="changeColor"
          :style="{ backgroundColor: completed ? 'darkgreen' : 'darkred' }"
        >
          <h2>{{ title }}</h2>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['title', 'id', 'completed'],
    methods: {
      deleteById() {
        this.$emit('deleteById', this.id)
      },
      changeColor() {
        this.$emit('changeColor', this.id)
      }
    }
  }
  </script>
  
  <style scoped>
  .todo_item {
    display: flex;
    flex-direction: column;
    padding: 10px 20px;
    justify-content: center;
    align-items: center;
    width: 35%;
    margin: 17px;
    border-radius: 4px;
    color: white;
  }
  </style>
  