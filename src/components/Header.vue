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
    .bg{
        background-color:#2e3a46;
        height: 100px;

        img{
            width: 260px;
        }
    }
</style>