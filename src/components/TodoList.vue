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
export default {
  name: "TodoList",
  props: {
    todo: {
      type: Array,
      required: true,
    }
  },
  methods: {
  }
}
</script>
