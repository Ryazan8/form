<template>
  <form @submit.prevent class="form">
    <h2 class="create-worker">Добавление сотрудников:</h2>
    <my-input
      v-model="worker.name"
      type="text"
      placeholder="Имя" />
    <my-input
        v-model="worker.age"
        type="number"
        placeholder="Возраст" />
    <my-button
      style="align-self: flex-start; margin-top: 15px;"
      @click="createWorker"
    >
      Добавить
    </my-button>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
import MyInput from "@/components/UI/MyInput.vue";
export default {
  components:{
    MyInput,MyButton
  },
  data() {
    return{
      worker: {
        name: '',
        age: '',
      }
    }
  },
  methods: {
    createWorker() {
      this.worker.id = Date.now()
      this.$emit('create', this.worker)
      this.worker = {
        name: '',
        age: ''
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
.create-worker{
  text-align: center;
  margin-top: 15px;
}
</style>