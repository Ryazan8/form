<template>
  <div>
    <h2 class="title-list-product">Список товаров:</h2>
    <product-item
      v-for="product in products"
      :product="product"
      :key="product.id"
    />
  </div>
</template>

<script>
import ProductItem from "@/components/ProductItem.vue";
export default {
  components: {
    ProductItem
  },
  props:{
    products: {
      type:Array,
      required: true
    }
  }


}
</script>

<style scoped>
.title-list-product{
  margin-top: 15px;
  text-align: center;
}
</style>