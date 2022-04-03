<template>
  <div class="mb-2 d-flex">
    <div>
      <input type="checkbox"
             :checked="todoList.checked"
             @change="toggleCheckbox">
    </div>

    <span class="ml-3 flex-grow-1"
          :class="todoList.checked ? 'text-muted' : ''"
          :style="todoList.checked ? 'text-decoration:line-through' : ''">
      {{ todoList.text }}
    </span>
    <button class="btn btn-danger btn-sm"
            @click="clickDelete">delete
    </button>
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
    },
    clickDelete() {
      this.$emit('click-delete', this.todoList.id)
    }
  }
}
</script>
