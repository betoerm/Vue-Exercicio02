<template>

  <form>
      <input type="text" v-model='nome' name="nome" id="nome" placeholder="Produto">
      <input type="text" v-model='descricao' name="descricao" id="descricao" placeholder="Descricao">
      <input type="button" v-on:click="addProd()" value="Enviar">
      <p class="valid" v-if=isNameLimitExceeded>O nome do produto não pode ultrapassar os 15 caracteres</p>
  </form>  
</template>

<script>
export default {
  name: 'ProductForm',
  data(){
    return {
      nome:'',
      descricao:'',
      isNameLimitExceeded: false
    }
  },
  props:{
    addProdParent:{ type: Function },
  },
  methods:{
    addProd(){
      if(!this.isNameLimitExceeded){
        this.addProdParent({
          produto:this.nome,
          descricao:this.descricao,
        })
      }
    }
  },
  watch:{
    nome(){
      if(this.nome.length > 15){
        this.isNameLimitExceeded = true
      }else{
        this.isNameLimitExceeded = false
      }
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.valid{
  color: red;
}
</style>
