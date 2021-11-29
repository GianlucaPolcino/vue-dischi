<template>
  <div>
    <Header @sendSearch="typeSearch" />
    <Main :songGenre="songGenre"/>
  </div>
  
</template>

<script>
import Header from "./components/Header.vue"
import Main from "./components/Main.vue"

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },

  data(){
    return{
      songGenre: '',
    }
  },

  methods:{
    typeSearch(type){
      return this.songGenre = type;
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

</style>
