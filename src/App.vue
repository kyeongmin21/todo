<template>
  <div id="app">
    <h1 class="text-center">Todo App</h1>
    <input type="text"
           placeholder="text"
           class="w-100 p-2"
           @keyup.enter="addTodo"
          v-model="clearText">
    <hr>
    <Todo v-for="todo in todos" :key="todo.id"
          :todoList="todo"
          @toggle-checkbox="toggleCheckbox"
          @click-delete="clickDelete">

    </Todo>
  </div>
</template>

<script>
import Todo from '@/components/Todo'
export default {
  components: {Todo},
  data() {
    return {
      clearText: '',
      todos: [
        { id: 1, checked: true, text: 'study hard'},
        { id: 2, checked: false, text: 'buy a car'}
      ]
    }
  },
  methods: {
    addTodo(e) {
      this.todos.push({
        id: Math.random(),
        checked: false,
        text: e.target.value
      });
      this.clearText = ''
    },
    toggleCheckbox({id, checked}) {
      const index = this.todos.findIndex(todo =>{
        return todo.id === id
      })
      this.todos[index].checked = checked
    },
    clickDelete(id) {
      const index = this.todos.findIndex(todo => {
        return todo.id === id
      })
      this.todos.splice(index, 1)
    }
  }
}
</script>