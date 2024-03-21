
<script>
  export default {
    data(){
      return{

      }
    }
  }
</script>

<template>
  <header>
    <div class="container d_flex">
      <nav class="d_flex debug">
        <ul class="d_flex">
          <li><a href="">Donna</a></li>
          <li><a href="">Uomo</a></li>
          <li><a href="">Bambini</a></li>
        </ul>
      </nav>
      <div class="logo d_flex debug">
        <img src="../assets/img/boolean-logo.png" alt="">
      </div>
      <nav class="d_flex debug" id="nav_right">
        <ul class="d_flex">
          <li><a href=""><i class="fa-brands fa-square-facebook"></i></a></li>
          <li><a href=""><i class="fa-regular fa-heart"></i></a></li>
          <li><a href=""><i class="fa-solid fa-bag-shopping"></i></a></li>
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
    }
  }






  
</style>