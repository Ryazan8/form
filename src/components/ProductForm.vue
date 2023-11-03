<template>
  <form @submit.prevent class="form">
    <h2 class="create-product">Добавление товаров:</h2>
    <my-input
      v-model="product.name"
      type="text"
      placeholder="Название товара"
    />
    <my-input
        v-model="product.price"
        type="number"
        placeholder="Цена"
    />
    <my-button
        style="align-self: flex-start; margin-top: 15px"
        @click="createProduct"
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
    MyButton,MyInput
  },
  data() {
    return{
      product: {
        name: '',
        price: ''
      }
    }
  },
  methods: {
    createProduct() {
      this.product.id = Date.now()
      this.$emit('create', this.product)
      this.product = {
        name: '',
        price: ''
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

.create-product{
  text-align: center;
  margin-top: 15px;
}
</style>