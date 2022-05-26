<template>
  <div class="header">
    <div class="header-logo">
        <img :src="require('../assets/logo.png')" alt="">
    </div>  
    <div class="header-text">
        <input type="text" placeholder="Inserisci un titolo" v-model="searchMovie">
        <button @click="$emit('startSearch', searchMovie)">Cerca</button>
    </div>  
  </div>
</template>

<script>
export default {
    name: "AppHeader",
    data() {
        return {
            searchMovie: ""
        }
    }
}
</script>

<style lang="scss" scoped>
 .header {
     height: 80px;
     background-color: #141414;
     display: flex;
     justify-content: space-between;
     align-items: center;
     padding: 2rem;

    .header-text {
        input {
            padding: .2rem;
        }
   
        button {
            padding: .2rem .5rem;
            margin-left: .2rem;
        }

    }

    .header-logo > img {
        width: 80%;
    }
 }
</style>