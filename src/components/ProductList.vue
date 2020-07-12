<template>
  <div>
        <p v-for="p in products" v-bind:key="p.nome"> 
          <ProductItem v-bind:produto="p"/>
        </p>
  </div>
  
</template>

<script>
export default {
  name: 'ProductList',
  components: {
    ProductItem
  },
  props:{
    products: Array
  },  
}
import ProductItem from './ProductItem.vue'
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
