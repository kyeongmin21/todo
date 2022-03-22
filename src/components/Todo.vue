<template>
  <div>
    {{ todo.checked }}
    <input type="checkbox"
           :checked="todo.checked"
           @change="toggleCheckbox">
    <span class="ml-3"
          :class="todo.checked ? 'text-muted' : '' "
          :style="todo.checked ? 'text-decoration: line-through' : '' ">
          {{ todo.text }}
    </span>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    toggleCheckbox(e) {
      this.$emit('toggle-checkbox', {
        id: this.todo.id,
        checked: e.target.checked
      })
    },
  }
}
</script>
