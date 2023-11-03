<template>
  <form @submit.prevent class="form">
    <h2 class="create-todo">Создание заметок:</h2>
    <div class="todo-form">
      <my-input
          class="todo-input"
          v-model="todo.title"
          type="text"
          placeholder="Название"
      />
      <my-button
          style="align-self: flex-end; margin-top: 15px"
          @click="createToDo"
      >
        +
      </my-button>
    </div>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
import MyInput from "@/components/UI/MyInput.vue";
export default {
  components: {
    MyButton, MyInput
  },
  data() {
    return{
      todo: {
        title: '',
      }
    }
  },
  methods: {
    createToDo() {
      this.todo.id = Date.now()
      this.$emit('create', this.todo)
      this.todo = {
        title: '',
      }
    }
  }
}
</script>

<style scoped>
.form{
  max-width: 250px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
}

.create-todo{
  text-align: center;
  margin-top: 15px;
}

.todo-input{
  margin-right: 15px;
}

.todo-form{
  display: flex;
}

</style>