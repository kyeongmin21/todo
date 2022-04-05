<template>
  <div>
    {{ todoList.checked }}
    <input type="checkbox"
           :checked="todoList.checked"
           @change="toggleCheckbox">
    <span class="ml-2"
          :class="todoList.checked ? 'text-muted' : '' "
          :style="todoList.checked ? 'text-decoration: line-through' : '' ">{{ todoList.text }}</span>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todoList: {
      type: Object,
      required: true
    }
  },
  methods: {
    toggleCheckbox(event) {
      this.$emit('toggle-checkbox', {
        id: this.todoList.id,
        checked: event.target.checked
      })
    }
  }
}
</script>
