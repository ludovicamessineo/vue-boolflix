<template>
  <section>
      <ul>
          <AppCard v-for="item in movies" :key="item.id" :movie="item"/>
      </ul>
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
        movies: Array
    }
}
</script>

<style lang="scss" scoped>

</style>