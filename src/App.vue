<template>
  <div id="app">
 <HeaderComponent @sendInputText="saveInputText" />
<MainComponent :movies='myMoviesArray' :series='mySeriesArray'/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import axios from 'axios';



export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
   },

 data() {
    return {
      textInput:"",
      myKey: "3afc5e2a3dde3b9297d1aa3a09bb22dd",
      myMoviesArray: [],
      mySeriesArray: [],
    }
 },

  methods:{
    saveInputText (value){
      this.textInput = value
      this.callApiMovies()
      this.callApiSeries()
    },
    callApiMovies (){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.myKey}&query=${this.textInput}`)
      .then((response) => {
        if (this.textInput.length > 0) {
          this.myMoviesArray = response.data.results
        }
      })
    },

    callApiSeries (){
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${this.myKey}&query=${this.textInput}`)
      .then((response) => {
        console.log(response)
        if (this.textInput.length > 0) {
          this.mySeriesArray = response.data.results
        }
      })
  }
}
}


</script>

<style lang="scss">
#app {box-sizing: border-box;
  margin: 0;
  padding: 0;

}
</style>
