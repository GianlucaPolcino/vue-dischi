<template>
  <div class="card d-flex align-items-center p-4">
      <img class="pb-3" src="https://m.media-amazon.com/images/I/91s+CxEDriL._AC_SY450_.jpg" alt="">
      <h4 class="text-white fw-bold">TITOLO CANZONE</h4>
      <p>Artista</p>
      <span>Anno</span>
  </div>
</template>

<script>
export default {
    name: "Cards",
}
</script>

<style lang="scss">
    @import "../assets/style/vars.scss";

    .card{
        background-color: $light-color;

        img{
            width: 100%;
        }
        
        
    }
</style>