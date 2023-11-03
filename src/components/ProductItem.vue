<template>
  <div class="product">
    <div>
      <div><strong>Название:</strong>{{ product.name }}</div>
      <div><strong>Цена:</strong>{{ product.price }}</div>
    </div>

  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
 components: {
   MyButton
 },
  props:{
   product:{
     type: Object,
     required: true
   }
  }
}
</script>

<style scoped>
.product{
  padding: 15px;
  border: 2px dotted #cf5353;
  margin: 15px auto;
  max-width: 500px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>