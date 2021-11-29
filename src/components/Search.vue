<template>
  <div>
        <select class="form-select" aria-label="Default select example" 
        v-model="type" @change="$emit('change', type)">
            <option value="all">Tutti i generi</option>
            <option value="pop">Pop</option>
            <option value="rock">Rock</option>
            <option value="metal">Metal</option>
            <option value="jazz">Jazz</option>
      </select>
  </div>
</template>

<script>
export default {
    name: "Search",

    data(){
        return{
            type: 'all',
        }
    },
}
</script>

<style lang="scss"> 

</style>