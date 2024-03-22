
<script>
  export default {
    data(){
      return{
        // fatto con dati presenti in componente 
        navLeft :[
          {
            genere : 'Donna',
            link: '#'
          },
          {
            genere : 'Uomo',
            link: '#'
          },
          {
            genere : 'Bambini',
            link: '#'
          },
        ],
        navRight :[
          {
            icon : '<i class="fa-regular fa-user"></i>',
            link: '#'
          },
          {
            icon : '<i class="fa-regular fa-heart"></i>',
            link: '#'
          },
          {
            icon : '<i class="fa-solid fa-bag-shopping"></i>',
            link: '#'
          },
        ],
        img: {
          path: 'boolean-logo.png',
          title: 'logo'
        }
      }
    },

    methods:{
      getImagePath(img){
        return new URL (`../assets/img/${img}`, import.meta.url).href
      }
    }
  }
</script>

<template>
  <header>
    <div class="container d_flex">
      <nav class="d_flex debug">
        <ul class="d_flex">
          <li v-for="(nav, indice) in navLeft" :key="`nl-${indice}`"><a :href="nav.link">{{ nav.genere }}</a></li>
        </ul>
      </nav>
      <div class="logo d_flex debug">
        <img :src=getImagePath(img.path) :alt="img.title">
      </div>
      <nav class="d_flex debug" id="nav_right">
        <ul class="d_flex">
          <li v-for="(nav, indice) in navRight" :key="`nr-${indice}`"><a :href="nav.link" v-html="nav.icon"></a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
  @use '../assets/scss/partials/variables' as *;

  header{
    width: 100%;
    height: 80px;
    background-color: $header-color;
    box-shadow: $box-shadow;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;
    .container{
      height: 100%;
      align-items: center;
      justify-content: space-between;
      nav{
        width: calc(100% / 3 );
      }
      .logo{
        align-items: center;
        justify-content: center;
        width: 20%;
        
      }
      #nav_right{
        justify-content: flex-end;
      }
    }
  }






  
</style>