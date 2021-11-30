<template>
  <div class="container-fluid bg">
      <div class="row align-items-center justify-content-between">
          <div class="col p-2">
                <img src="../assets/img/logo.png" alt="">
          </div>
          <div class="col-4">
                <Search @change="performSearch"/>
          </div>
      </div>
  </div>
</template>

<script>
import Search from "./Search.vue"

export default {
    name: "Header",
    components:{
        Search,
    },

    data(){
        return{
            typeToSearch: '',
        }
    },

    methods:{
        performSearch(type){
            this.typeToSearch = type;
            // console.log(this.typeToSearch);
            return this.$emit('sendSearch', this.typeToSearch)
        }
    },
}
</script>

<style lang="scss">
    @import "../assets/style/vars.scss";

    .bg{
        background-color: $light-color;
        height: 100px;

        img{
            width: 260px;
        }
    }
</style>