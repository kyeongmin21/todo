<template>
  <div>
    <input type="checkbox" :checked="todo.checked">
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
  }
}
</script>
