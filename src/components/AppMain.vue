<template>
  <section>
      <div class="container">
        <h2>Film</h2>  
        <ul class="show-wrapper">
            <AppCard v-for="item in movies" :key="item.id" :showObj="item"/>
        </ul>

        <h2>Serie Tv</h2>
        <ul class="show-wrapper">
            <AppCard v-for="item in series" :key="item.id" :showObj="item"/>
        </ul>
      </div>
  </section>
</template>

<script>
import AppCard from './AppCard.vue'
export default {
    name: "AppMain",
    components: {
        AppCard
    },
    props: {
        movies: Array,
        series: Array
    }
}
</script>

<style lang="scss" scoped>

.show-wrapper {
    display: flex;
    flex-wrap: wrap;
}

h2 {
    margin: 1rem;
    font-size: 2rem;
}
</style>