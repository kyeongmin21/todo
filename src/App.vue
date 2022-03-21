<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input type="text" class="w-100 p-2" placeholder="Type todo">
    <hr>
    <Todo v-for="todo in todos" :key="todo.id"></Todo>
  </div>
</template>
<script>
import Todo from '@/components/Todo'
export default {
  components: {
    Todo
  },
  data() {
    return {
      todos: [
        { id: 1, text: 'buy a car', checked: false },
        { id: 2, text: 'play game', checked: false }
      ]
    }
  }
}
</script>