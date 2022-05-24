<template>
  <li>
    <h2>{{ movie.title}}</h2>
    <h4>{{ movie.original_title }}</h4>
    <p>{{ movie.original_language }}</p>
    <small>{{ movie.vote_average}}</small>
  </li>
</template>

<script>

export default {
    name: "AppCard",
    props: {
      movie: Object
    }
}
</script>

<style>

</style>