<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input v-model="clearText"
           type="text" class="w-100 p-2"
           placeholder="Type todo"
           @keyup.enter="addTodo">
    <hr>
    <Todo v-for="todo in todos"
          :key="todo.id"
          :todo="todo"
          @toggle-checkbox="toggleCheckbox"/>
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
        {id: 1, text: 'buy a car', checked: true},
        {id: 2, text: 'play game', checked: false}
      ],
      clearText: '',
    }
  },
  methods: {
    addTodo(e) {
      this.todos.push({
        id: Math.random(),
        text: e.target.value,
        checked: false
      });
      this.clearText = '';
    },
    toggleCheckbox({id, checked}) {
      console.log(id, checked)
    }
  }
}
</script>