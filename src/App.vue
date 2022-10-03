<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  
      <nav>
        
       
      </nav>
    
      <div class="container">
        <ul>
        <RouterLink to="/"><li>Todo List</li></RouterLink>
        <RouterLink to="/new"><li>New Todo</li></RouterLink>

      </ul>

        <RouterView />
      </div>
</template>

<style scoped>
@import './assets/base.css';
</style>
