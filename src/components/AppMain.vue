<template>
  <section>
      <div class="container">
        <h1>Film</h1>  
        <ul class="show-wrapper">
            <AppCard v-for="item in movies" :key="item.id" :showObj="item"/>
        </ul>

        <h1>Serie Tv</h1>
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
</style>