<template>
  <div class="worker">
    <div>
      <div><strong>Имя:</strong>{{ worker.name }}</div>
      <div><strong>Возраст:</strong>{{ worker.age }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    worker: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.worker{
  padding: 15px;
  border: 2px dotted #cf5353;
  margin: 15px auto;
  max-width: 500px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>