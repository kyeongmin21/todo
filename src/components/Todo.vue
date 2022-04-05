<template>
  <div>
    <input type="checkbox">
    <span class="ml-2">{{ todoList.text }}</span>
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

  }
}
</script>
