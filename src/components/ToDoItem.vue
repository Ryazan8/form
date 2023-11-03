<template>
  <div class="todo">
    <div><strong>Задача:</strong>{{ todo.title }}</div>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>
.todo{
  padding: 15px;
  border: 2px dotted #cf5353;
  margin: 15px auto;
  max-width: 500px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>