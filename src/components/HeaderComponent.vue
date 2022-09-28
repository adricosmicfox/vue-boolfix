<template>
  <header>
<div class="am- logobox h-100 px-5 d-flex align-items-center justify-content-between">
    <img src="../assets/Logonetflix.png" alt="">
    <div class="d-flex gap-3">
        <input class="rounded-pill"
         type="text" placeholder="  Ricerca serie o film per titolo" v-model="searchText"> 
        <button @click="$emit('sendInputText', searchText)" class="btn btn-danger rounded-pill">Search</button>
    </div>
    
</div>

  </header>
</template>

<script>
export default {
    name: 'HeaderComponent',
    data(){
        return{
            searchText:''
        }
    }
}
</script>

<style lang="scss" scoped>
    header {
        height: 10vh;
        min-width: 100%;
        background-color: transparent;
        position: fixed;
       

        img{
            width: 15rem;
        }

        input{
            width: 20rem;
            height: 3rem;
        }

    }

</style>