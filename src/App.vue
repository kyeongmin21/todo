<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input type="text" class="w-100 p-2"
           placeholder="todo list"
           @keyup.enter="addTodo"
           v-model="cleanText">
    <hr>
    <Todo v-for="todo in todos"
          :key="todo.id"
          :todoList="todo"
          @toggle-checkbox="toggleCheckbox"></Todo>
  </div>
</template>

<script>
import Todo from '@/components/Todo'
export default {
  components: {Todo},
  data() {
    return {
      cleanText: '',
      todos: [
        { id: 1, text: 'study hard', checked: true} ,
        { id: 2, text: 'buy a car', checked: false },
      ]
    }
  },
  methods: {
    addTodo(event) {
      this.todos.push(
      { id: Math.random(), text: event.target.value, checked: false }
      )
      this.cleanText =''
    },
    toggleCheckbox({id, checked}) {
      const index = this.todos.findIndex( todo => {
        return todo.id === id
      })
      this.todos[index].checked = checked
    }

  }
}
</script>