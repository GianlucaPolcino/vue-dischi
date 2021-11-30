<template>
  <div class="container-fluid bg-main">
      <div class="container py-5">
          <div class="row justify-content-center" v-if="loaded == false">
              <Cards 
              v-for="(song, index) in filteredSongs" :key="index" :song="song"
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
    props:{
        songGenre: String
    },
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
        },

        

        },
    

    mounted(){
        this.getApi();
    },

    computed:{
        filteredSongs(){
            if(this.songGenre == 'all' || this.songGenre == '' ){
                return this.songs;
            }else{

                let arrayGenre = [];

                for(let i = 0; i < this.songs.length -1; i++){
                    if(this.songs[i].genre.toUpperCase().includes(this.songGenre.toUpperCase()))
                    arrayGenre.push(this.songs[i]);
                }

                return arrayGenre;
            }                

            
        },
    }
}
</script>

<style lang="scss">
    .bg-main{
        background-color: #1e2d3b;
        min-height: 100vh
    }
</style>