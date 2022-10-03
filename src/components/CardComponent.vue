<template>

  <section>

    <div v-if="!this.active" @click="changeStatus()" class="poster">
      <img class="w-100 h-100" v-if="arrayElement.poster_path" :src="baseUrl+arrayElement.poster_path" :alt="arrayElement.title ? arrayElement.title : arrayElement.name">
      <img v-else src="../assets/no_poster.jpg" alt="Poster-not-available" class="am-noposter">
    </div>

    <div v-else @click="changeStatus()" class="informations d-flex p-3 flex-column">
      <div> 
        <h3> Titolo:</h3> 
        {{arrayElement.title ? arrayElement.title : arrayElement.name}}
      </div>
      <div> 
      <h3> Titolo originale:</h3> 
        {{arrayElement.title ? arrayElement.original_title : arrayElement.original_name}}
      </div>

      <div>
        <div v-if="arrayElement.original_language === 'it'">
          <h4>Lingua:</h4>
          <span :class="`fi fi-it`"></span>
        </div>
        <div v-else-if="arrayElement.original_language === 'es'">
          <h4>Lingua:</h4>
          <span :class="`fi fi-es`"></span>
        </div>
        <div v-else-if="arrayElement.original_language === 'en'">
          <h4>Lingua:</h4>
          <span :class="`fi fi-gb`"></span>
        </div>
        <div v-else-if="arrayElement.original_language === 'ja'">
          <h4>Lingua:</h4>
          <span :class="`fi fi-jp`"></span>
        </div>
        <div v-else-if="arrayElement.original_language === 'fr'">
          <h4>Lingua:</h4>
          <span :class="`fi fi-fr`"></span>
        </div>
        <div v-else>
          <h4>Lingua:</h4>
          {{ arrayElement.original_language }}
        </div>
      </div>
    </div>

    

  </section>

</template>





<script>
export default {
name: "CardComponent",
props:["arrayElement"],
data(){
    return {
        baseUrl:"https://image.tmdb.org/t/p/w300",
        active:false
    }
},

methods: {
  changeStatus() {
    this.active = !this.active
  }
}


}
</script>




<style lang="scss" scoped>
@import "~@fortawesome/fontawesome-free/css/all.min.css";

.informations{
  color: white;
  height: 450px;
  width: 300px;
  border-radius: 20px;
  background-color: rgba(0, 0, 0, 0.525);
  box-shadow: 1px 4px 30px 5px #e9e7e7ad;
  }

.am-noposter {
    height: 450px;
    width: 300px;
}

.poster{
  height: 450px;
  width: 300px;
}

img{
  border-radius: 20px;
}


</style>