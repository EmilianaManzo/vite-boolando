<script>
  export default {
    props:{
      // richiamo product e gli dico che è un oggetto 
      product : Object

    },

    data(){
      return{
        finalPrice: ''
      }
    },

    methods:{
      getImagePath(img){
        return new URL (`../../assets/img/${img}`, import.meta.url).href
      },

      getDiscount(product){
        product.badges.forEach(badge => { 
          
          if(badge.value == '-50%'){
          this.finalPrice = (product.price - (product.price * 0.50)).toFixed(2)
  
          }else if(badge.value == '-30%'){
           this.finalPrice = (product.price -  (product.price * 0.30)).toFixed(2)
          }
          
        })
        
        return this.finalPrice

      }
    },

    mounted(){
  
    }
  }
</script>


<template>
  <div class="col">
    <div class="card">
              
              <div class="card-images">
                <img :src="getImagePath(product.frontImage)" :alt="product.frontImage">
                <img class="secondary-image" :src="getImagePath(product.backImage)" :alt="product.backImage">
                <div class="favourite" :class="{'whishlist': product.isInFavorites}" @click=" product.isInFavorites = !product.isInFavorites">
                  <i class="fa-solid fa-heart"></i>
                </div>
                <div class="badges" >
                  <!-- mi mette prima sostenibilità e poi la percentuale di sconto perche sono cosi nel database, ma se volessi metterli al contrario? -->
                  <span class="badge" v-for="(badge, indice) in product.badges" :class="badge.type" :key="`b-${indice}`">{{ badge.value }}</span>
                </div>
              </div>
              
              <div class="card-text">
                <div class="brand">{{ product.brand }}</div>
                <div class="product-name">{{ product.name }}</div>
                <div class="price">
                  <span class="new_price" v-if= "getDiscount(product)">{{ getDiscount(product) }} &euro;</span>
                  <span class="new_price" :class="{'old_price':getDiscount(product)}">{{ product.price }}&euro;</span>
                </div>
              </div>
            </div>
  </div>
</template>


<style lang="scss" scoped>
  @use '../../assets/scss/partials/general' as *;

  .card {
    margin-bottom: 20px;
    .card-images{
        position: relative;
        cursor: pointer;

        .secondary-image{
          display: none;
          position: absolute;
          top:0;
          left: 0;
        }

        &:hover .secondary-image{
          display: block;
        }

        .favourite{
          position: absolute;
          background-color: white;
          top: 20px;
          right: 0;
          padding: 21px 14px;

          &:hover{
            color: red;
          }
        }

        .whishlist{
          color: red;
        }
    }

    .badges{
      position: absolute;
      bottom: 15px;
      left: 0;

      .badge{
        padding: 5px 10px;
        color: white;
        font-weight: 700;
        text-transform: capitalize;

        &.discount{
          margin-right: 30px;
          background-color: red;
        }

        &.tag{
          background-color: green;
          margin-right: 5px;
        }

      }
    }

    .card-text {
      .product-name{
        font-weight: 700;
        text-transform: uppercase;
      }

      .price{
        font-size: .9rem;
      }

      .new_price{
        color: red;
        font-weight: 700;
        padding-right: 10px;
      }

      .old_price{
        text-decoration: line-through;
        color: black;
        font-weight: normal;
      }


    }
  
}

</style>