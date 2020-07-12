<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <ProductList v-bind:products=products />    
    <ProductForm :addProdParent="pushProduct" />
    Total de Produtos: {{totalProducts}}
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ProductList from './components/ProductList.vue'
import ProductForm from './components/ProductForm.vue'

export default {
  name: 'App',  data(){
    return {
      products:[
        {
          produto:'p1',
          descricao:'d1',
        }
      ]
    }
  },
  computed: {
    totalProducts:function(){
      return this.products.length;
    }
  },
  methods:{
    pushProduct(prod){
      this.products.push(prod)
    }
  },
  components: {
    HelloWorld,
    ProductList,
    ProductForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
