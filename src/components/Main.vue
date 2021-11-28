<template>
  <div class="container-fluid bg-main">
      <div class="container py-5">
          <div class="row justify-content-center" v-if="loaded == false">
              <Cards 
              v-for="(song, index) in songs" :key="index" :song="song"
              />
          </div>

          <div class="row" v-else>
              <div class="col text-center">
                  <h1 class="text-white">Caricamento...</h1>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import axios from "axios"

import Cards from "./Cards.vue"

export default {
    name: "Main",
    components:{
        Cards,
    },

    data(){
        return{
            songs: [],
            loaded: false,
            api: "https://flynn.boolean.careers/exercises/api/array/music",
        }
    },

    methods:{
        getApi(){
            this.loaded = true;
            axios.get(this.api)
            .then(r =>{
                this.songs = r.data.response;
                this.loaded = false;
            })
            .catch(e =>{
                console.log(e);
            })
        }
    },

    mounted(){
        this.getApi();
    }
}
</script>

<style lang="scss">
    .bg-main{
        background-color: #1e2d3b;
        min-height: 100vh
    }
</style>