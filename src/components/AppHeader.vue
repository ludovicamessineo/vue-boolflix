<template>
  <div class="header">
    <input type="text" placeholder="Inserisci un titolo" v-model="searchMovie">
    <button @click="$emit('startSearch', searchMovie)">Cerca</button>
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
     justify-content: flex-end;
     align-items: center;
     padding-right: 2rem;

     input {
         width: 15%;
         padding: .2rem;
     }

     button {
         padding: .2rem .5rem;
         margin-left: .2rem;
     }
 }
</style>