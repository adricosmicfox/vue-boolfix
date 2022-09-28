<template>
  <div>
    
    <img :src="baseUrl+arrayElement.poster_path">


  </div>



</template>






<script>
export default {
name: "CardComponent",
props:["arrayElement"],
data(){
    return {
        baseUrl:"https://image.tmdb.org/t/p/w185"
    }
}
}
</script>






<style lang="scss" scoped>



</style>