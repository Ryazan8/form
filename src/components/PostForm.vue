<template>
  <form @submit.prevent class="form">
    <h2 class="create-post">Создание поста:</h2>
    <my-input
        v-model="post.title"
        type="text"
        placeholder="Название"/>
    <my-input
        v-model="post.body"
        type="text"
        placeholder="Описание"/>

    <my-button
        style="align-self: flex-start; margin-top: 15px"
        @click="createPost"
        >
      Добавить
    </my-button>
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
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
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

.create-post{
  text-align: center;
  margin-top: 15px;
}



</style>