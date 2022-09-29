<template>

  <div>
    <img v-if="arrayElement.poster_path" :src="baseUrl+arrayElement.poster_path" :alt="arrayElement.title ? arrayElement.title : arrayElement.name">
    <img v-else src="../assets/no_poster.jpg" alt="Poster-not-available" class="am-noposter">
        <!-- <img :src="baseUrl+arrayElement.poster_path"> -->
  </div>


</template>





<script>
export default {
name: "CardComponent",
props:["arrayElement"],
data(){
    return {
        baseUrl:"https://image.tmdb.org/t/p/w300"
    }
}
}
</script>




<style lang="scss" scoped>

.am-noposter {
    height: 450px;
    width: 300px;
  }


</style>