<template>
  <div>
    {{ todoList.checked}}
    <input type="checkbox"
           :checked="todoList.checked">
    <span class="ml-3">{{ todoList.text }}</span>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todoList: {
      type: Object,
    }
  },
  methods: {

  }
}
</script>
