<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button'
}
</script>

<style scoped>
.btn{


  padding: 10px 15px;
  background: none;
  color: #cf5353;
  border: 1px solid #cf5353;
  cursor: pointer;
  transition: all .3s ease-in-out;
}

.btn:hover{
  color: #fff;
  border-radius: 5px;
  background-color: #cf5353;
}
</style>