<template>
  <div>
    <Todo v-for="todo in todos"
          :key="todo.id"
          :todo="todo"
          @toggle-checkbox="toggleCheckbox"
          @click-delete="deleteTodo"/>

  </div>
</template>

<script>
import Todo from '@/components/Todo'

export default {
  name: "TodoList",
  components: {
    Todo
  },
  props: {
    todos: {
      type: Array,
      required: true,
    }
  },
  methods: {
    toggleCheckbox(value) {
      this.$emit('toggle-checkbox', value)
    },
    deleteTodo(todoId) {
      this.$emit('click-delete',todoId)
    }
  }
}
</script>
