<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input type="text" class="w-100 p-2" placeholder="Type todo">
    <hr>
    <Todo></Todo>
  </div>
</template>
<script>
import Todo from '@/components/Todo'
export default {
  components: {
    Todo
  }
}
</script>