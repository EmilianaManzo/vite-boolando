<script>
  export default {
    props:{
      // richiamo product e gli dico che è un oggetto 
      product : Object

    },

    methods:{
      getImagePath(img){
        return new URL (`../../assets/img/${img}`, import.meta.url).href
      }
    }
  }
</script>


<template>
  <div class="col">
    <div class="card">
              
              <div class="card-images">
                <img :src="getImagePath(product.frontImage)" :alt="product.frontImage">
                <img class="secondary-image" :src="getImagePath(product.backImage)" :alt="product.backImage">
                <div class="favourite">
                  <i class="fa-solid fa-heart"></i>
                </div>
                <div class="badges">
                  <span class="badge discount">-50%</span>
                  <span class="badge tag">{{  }}</span>
                </div>
              </div>
              
              <div class="card-text">
                <div class="brand">Levi's</div>
                <div class="product-name">RELAXED fit tee UNISEX</div>
                <div class="price">
                  <span>14,99 &euro;</span>
                  <del>29,99 &euro;</del>
                </div>
              </div>
            </div>
  </div>
</template>


<style lang="scss" scoped>
  @use '../../assets/scss/partials/general' as *;


</style>