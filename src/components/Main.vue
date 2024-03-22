
<script>
  import ProductCard from './partials/ProductCard.vue';
  import dataproducts from '../assets/data/db.json';
  export default {
    components:{
      ProductCard
    },
    data(){
      return{
        dataproducts
      }
    },
    mounted(){
      console.log(this.dataproducts);
    }
  }
</script>

<template>
  <main>
    <div class="container">
      <div class="row">
      
        <ProductCard 
          v-for="product in dataproducts.products"
          :key="product.id"
          :product="product"
        />
        <!-- utilizzo :product="product" per passarmi l'oggetto ciclato in ProductCard -->
      </div>
    </div>
    
  </main>
</template>

<style lang="scss" scoped>
   @use '../assets/scss/partials/variables' as *;
  main{
    padding-top: 150px;
  }
</style>