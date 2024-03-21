
<script>
  export default {
    data(){
      return{
        lawPages: [
          {
            name: 'Informazioni legali',
            link: '#'
          },
          {
            name: 'Informazioni sulla privacy',
            link: '#'
          },
          {
            name: 'Diritto di recesso',
            link: '#'
          },
        ],

        icons:[
          {
            img: '<i class="fa-brands fa-square-twitter"></i>',
            link:'https://twitter.com/'
          },

          {
            img: '<i class="fa-brands fa-square-facebook"></i>',
            link:'https://www.facebook.com/'
          },

          {
            img: '<i class="fa-brands fa-instagram"></i>',
            link:'https://www.instagram.com/'
          },

          {
            img: '<i class="fa-brands fa-square-pinterest"></i>',
            link:'https://www.pinterest.it/'
          },

          {
            img: '<i class="fa-brands fa-square-youtube"></i>',
            link:'https://www.youtube.com/'
          },
        ]
      }
    }
  }
</script>

<template>
  <footer>
    <div class="container d_flex">
      <div class="left_footer debug">
        <h3>Boolean s.r.l.</h3>
        <nav class="law_pages">
          <ul class="d_flex">
            <li v-for="(elem, indice) in lawPages" :key="indice"><a :href="elem.link">{{ elem.name }}</a></li>
          </ul>
        </nav>
      </div>
      <div class="right_footer d_flex debug">
        <div class="social">
        <h5>Trovaci anche su </h5>
        </div>
        <nav class="icons">
          <ul class="d_flex">
            <li v-for="(icon, indice) in icons" :key="indice">
              <a :href="icon.link" target="_blank" v-html="icon.img"></a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
   @use '../assets/scss/partials/variables' as *;

  footer{
    background-color: $footer-color;
    height: 100px;
    width: 100%;  
    .container{
      height: 100%;
      justify-content: space-between;
      align-items: center;
      .left_footer,
      .right_footer{
        width: calc(100% / 2);
      }
      .left_footer h3,
      .right_footer h5{
      color: $text-light;
      margin: 10px 0;
      }
      .left_footer{
        .law_pages ul li a{
            color: $text-light;
            font-weight: lighter;
            font-size: .6em;
            padding-right: 10px;
            text-decoration: none;
            cursor: pointer;
          }
      }
      .right_footer{
        flex-direction: column;
        align-items: flex-end;
        h5{
          padding-right: 15px;
        }
      }

    }
  }

</style>