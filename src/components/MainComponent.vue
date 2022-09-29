<template>
  <main>

    <div class="container d-flex flex-wrap gap-4"> 
      <CardComponent :arrayElement="film" v-for='film in movies' :key="film.id" />

      <CardComponent :arrayElement="serie" v-for="serie in series" :key="serie.id" />

    </div>
  
  </main>
</template>

<script>
import CardComponent from './CardComponent.vue'

export default {
    name: "MainComponent",
    components: {
      CardComponent
    },
    props: {
      movies:Array,
      series:Array

    }

}
</script>

<style lang="scss" scoped>
  main{
    background-image: url(../assets/Background.jpg);
    height: 100vh;
    background-size: cover;
    background-repeat: no-repeat;
    overflow-y: auto;
    padding-top: 10vh;

div{
  
 
  
}

  }

</style>