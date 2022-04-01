<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input type="text"
           class="w-100 p-2"
           placeholder="Type todo"
           @keyup.enter="addTodo">
    <hr>
    <Todo v-for="todo in todos"
          :key="todo.id"
          :todoList="todo">
    </Todo>
  </div>
</template>

<script>
import Todo from "@/components/Todo"
export default {
  components: {Todo},
  data() {
    return {
      todos: [
        {id: 1, text: 'study hard', checked: true},
        {id: 2, text: 'buy a car', checked: false},
      ]
    }
  },
  methods: {
    addTodo(e) {
      this.todos.push(
      {id: Math.random(), text: e.target.value, checked: false}
      )
    }
  }
}
</script>