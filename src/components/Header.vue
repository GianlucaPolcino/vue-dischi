<template>
  <div class="container-fluid bg">
      <div class="row">
          <div class="col p-2">
                <img src="../assets/img/logo.png" alt="">
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "Header",
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