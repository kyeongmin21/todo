<template>
  <div id="app" class="p-2">
    <h1 class="text-center">Todo App</h1>
    <input type="text" placeholder="텍스트를 입력해주세요."
           class="p-2 w-100"
          @keyup.enter="addTodo"
          v-model="clearText">
    <hr>

    <Todo v-for="todo in todos" :key="todo.id"
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
      clearText: '',
      todos: [
        { id: 1, checked: true, text: 'buy a car'},
        { id: 2, checked: false, text: 'study hard'}
      ]
    }
  },
  methods: {
    addTodo(event) {
      this.todos.push({
        id: Math.random(),
        checked: false,
        text: event.target.value
      })
      this.clearText = ''
    },
    toggleCheckbox({id, checked}) {
      const index = this.todos.findIndex(todo => {
        return todo.id === id
      })
      this.todos[index].checked = checked
    }
  }
}
</script>