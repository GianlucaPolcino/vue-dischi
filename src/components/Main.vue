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
          <div>
              <p>{{this.songGenre}}</p>
          </div>
      </div>
  </div>
</template>

<script>
import axios from "axios"

import Cards from "./Cards.vue"

export default {
    name: "Main",
    props:{
        songGenre: String
    },
    components:{
        Cards,
    },

    data(){
        return{
            songs: [],
            arrayGenre: [],
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
        },

        filteredSongs(){
            if(this.songGenre === 'all'){
                return this.songs;
            }
            this.arrayGenre = this.songs.filter(item =>{
            return item.genre.toUpperCase().includes(this.songGenre.toUpperCase());
            
            })

            return this.arrayGenre
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