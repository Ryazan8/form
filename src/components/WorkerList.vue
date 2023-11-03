<template>
  <div>
    <h2 class="title-list-worker">Список сотрудников:</h2>
    <worker-item
      v-for="worker in workers"
      :worker="worker"
      :key="worker.id"
    />
  </div>
</template>

<script>
import WorkerItem from "@/components/WorkerItem.vue";
export default {
  components: {
    WorkerItem
  },
  props: {
    workers: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.title-list-worker{
  margin-top: 15px;
  text-align: center;
}
</style>