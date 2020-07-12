<template>
  <div>
      <h4>
        {{produto.produto}}
      </h4>
      {{produto.descricao}}
      
  </div>
  
</template>

<script>
export default {
  name: 'ProductItem',
  props:{
    produto: Object
  },  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
