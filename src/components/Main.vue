<template>
  <div class="container-fluid bg-main">
      <div class="container">
          <div class="row">
              <div class="col-3 py-5">
                  <Cards />
              </div>
          </div>
      </div>
  </div>
</template>

<script>
import Cards from "./Cards.vue"

export default {
    name: "Main",
    components:{
        Cards,
    }
}
</script>

<style lang="scss">
    .bg-main{
        background-color: #1e2d3b;
        min-height: 100vh
    }
</style>