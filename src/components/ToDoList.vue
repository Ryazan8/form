<template>
  <div>
    <h2 class="title-list-todo">Список заметок:</h2>
    <to-do-item
      v-for="todo in todos"
      :todo="todo"
      :key="todo.id"
    />
  </div>
</template>

<script>
import ToDoItem from "@/components/ToDoItem.vue";
export default {
  components: {
    ToDoItem
  },
  props: {
    todos:{
      type: Array,
      required: true
    }
  }

}
</script>

<style scoped>
.title-list-todo{
  margin-top: 15px;
  text-align: center;
}
</style>