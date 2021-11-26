<template>
  <div class="card p-4 m-4 text-center">
      <img class="pb-3" :src="song.poster" alt="">
      <h4 class="text-white fw-bold">{{song.title}}</h4>
      <p>{{song.author}}</p>
      <span>{{song.year}}</span>
  </div>
</template>

<script>
export default {
    name: "Cards",
    props:{
        song: Object
    }
}
</script>

<style lang="scss" scoped>
    @import "../assets/style/vars.scss";

    .card{
        display: inline-block;
        width: 20%;
        min-height: 400px;
        background-color: $light-color;

        img{
            width: 100%;
        }

        p, span{
            color: gray;
        }
        
        
    }
</style>