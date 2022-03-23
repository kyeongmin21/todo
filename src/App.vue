<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input v-model="clearText"
           type="text" class="w-100 p-2"
           placeholder="Type todo"
           @keyup.enter="addTodo">
    <hr>

  </div>
</template>
<script>
import TodoList from "@/components/TodoList"

export default {
  components: {
    TodoList
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
      // console.log(id, checked)
      const index = this.todos.findIndex(todo => {
        return todo.id === id;
      })
      this.todos[index].checked = checked;
    },
    deleteTodo(id) {
      // const index = this.todos.findIndex(todo => {
      //   return todo.id === id;
      // })
      // this.todos.splice(index, 1)
      this.todos = this.todos.filter(todo => todo.id !== id)
    }

  }
}
</script>