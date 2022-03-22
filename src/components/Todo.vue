<template>
  <div>
    {{ todo.checked }}
    <input type="checkbox"
           :checked="todo.checked"
           @change="toggleCheckbox">
    <span class="ml-3" >{{ todo.text }}</span>
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
      this.$emit('toggleCheckbox', {
        id: this.todo.id,
        checked: e.target.checked
      })
    },
  }
}
</script>
