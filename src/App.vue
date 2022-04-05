<template>
  <div id="app" class="p-2">
    <h1 class="text-center">Todo List</h1>
    <input type="text" class="w-100 p-2"
           placeholder="텍스트를 입력해주세요.">
    <hr>
    <Todo v-for="todo in todos" :key="todo.id"
          :todoList="todo">

    </Todo>
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
        { id: 1, text: 'buy a car', checked: true },
        { id: 2, text: 'study hard', checked: false }
      ]
    }
  },
  methods: {

  }
}
</script>