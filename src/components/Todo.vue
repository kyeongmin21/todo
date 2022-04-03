<template>
  <div>
    {{ todoList.checked}}
    <input type="checkbox"
           :checked="todoList.checked"
           @change="toggleCheckbox">
    <span class="ml-3">{{ todoList.text }}</span>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todoList: {
      type: Object,
      required: true,
    }
  },
  methods: {
    toggleCheckbox(e) {
      this.$emit('toggle-checkbox', {
        id: this.todoList.id,
        checked: e.target.checked
      })
    }
  }
}
</script>
