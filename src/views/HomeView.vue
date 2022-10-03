<script setup>
  import todos from '../mock/todos';
  import { todosFactory } from '../todosSetup';

  const {todosIncompleted, todosCompleted, toggle, deleteTodo} = todosFactory();

</script>
<template>
  
  <h3>ToDo List</h3>
  <ul id="incomplete-tasks">
    <li v-for="todo in todosIncompleted" :key="todo.id" @click="toggle(todo.id)">
      <input type="checkbox">
        <label for="">{{ todo.name }}</label>
        <button class="delete" @click="deleteTodo(todo.id)">Delete</button>    
    </li>
  </ul>
  <h3>Completed</h3>
  <ul id="completed-tasks">
    <li v-for="todo in todosCompleted" :key="todo.id" @click="toggle(todo.id)">
      <input type="checkbox" checked>
        <label for="">{{ todo.name }}</label>
        <button class="delete" @click="deleteTodo(todo.id)">Delete</button>    
    </li>
  </ul>
</template>

<style scoped>
  

</style>