
<script>
  import ProductCard from './partials/ProductCard.vue';
  import products from '../assets/data/db.json';
  export default {
    components:{
      ProductCard
    },
    data(){
      return{
        products
      }
    },

    mounted(){
      console.log(this.products);
    }
  }
</script>

<template>
  <main>
    <div class="row">
      <ProductCard />
    </div>
  </main>
</template>

<style lang="scss" scoped>
   @use '../assets/scss/partials/variables' as *;
  main{
    padding-top: 150px;
  }
</style>