<script setup>
import { RouterLink, RouterView } from 'vue-router'
import todoService from './services/todosServices';
import { todosFactory } from './todosSetup';
import { ref } from 'vue';

const {update} = todosFactory();

const isLoading = ref(true);
async function prefetch() {
  update(await todoService.getTodos());
  isLoading.value = false;
}
prefetch();

</script>

<template>
  
      <nav>
        
       
      </nav>
    
      <div class="container">
        <h2 v-if="isLoading">Loading TODOs...</h2>
        <template v-if="!isLoading">
        <ul>
        <RouterLink to="/"><li>Todo List</li></RouterLink>
        <RouterLink to="/new"><li>New Todo</li></RouterLink>

      </ul>
        
        <RouterView />
        </template>
      </div>
</template>

<style scoped>
@import './assets/base.css';
</style>
