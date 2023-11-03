<template>
  <div class="app">
    <div class="posts-design">
      <post-form @create="createPost"/>
      <post-list :posts="posts" @remove="removePost"/>
    </div>
    <div class="todo-design">
      <to-do-form @create="createToDo"/>
      <to-do-list :todos="todos"/>
    </div>
    <div class="worker-design">
      <worker-form @create="createWorker"/>
      <worker-list :workers="workers"/>
    </div>
    <div class="product-design">
      <product-form @create="createProduct"/>
      <product-list :products="products"/>
    </div>

  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
import ToDoForm from "@/components/ToDoForm.vue";
import ToDoList from "@/components/ToDoList.vue";
import WorkerForm from "@/components/WorkerForm.vue";
import WorkerList from "@/components/WorkerList.vue";
import ProductForm from "@/components/ProductForm.vue";
import ProductList from "@/components/ProductList.vue";
export default {
  components: {
    PostForm,PostList,ToDoForm,ToDoList,WorkerForm,WorkerList,ProductForm,ProductList
  },

  data () {
    return{
      posts:[

      ],
      todos: [

      ],
      workers: [

      ],
      products: [

      ]
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    createToDo(todo) {
      this.todos.push(todo)
    },
    createWorker(worker) {
      this.workers.push(worker)
    },
    createProduct(product) {
      this.products.push(product)
    }
  }

}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.app{
  max-width: 1440px;
  margin: 0 auto;
}

.posts-design{
  background-color: #c9c9c9;
  padding-bottom: 30px;
}

.todo-design{
  background-color:  #b5b5b5;
  padding-bottom: 30px;
}
.worker-design{
  background-color:  #c9c9c9;
  padding-bottom: 30px;
}
.product-design{
  background-color:  #b5b5b5;
  padding-bottom: 30px;
}

</style>