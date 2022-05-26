<template>
  <li class="info-wrapper">
    <div class="card">
      <h2>{{ showObj.title ? showObj.title : showObj.name }}</h2>
      <h4>{{ showObj.original_title ? showObj.original_title : showObj.original_name }}</h4>
      <img v-if="addLangImg()" :src="require(`../assets/${showObj.original_language}.png`)" alt="">
      <p v-else> {{ showObj.original_language }} </p>
      <p>{{ showObj.vote_average}}</p>
    </div>
  </li>
</template>

<script>

export default {
    name: "AppCard",
    props: {
      showObj: Object
    },
    data() {
      return {
        flags: ["en", "es", "fr", "it"]
      }
    },
    methods: {
      addLangImg() {
        return this.flags.includes(this.showObj.original_language)
      }
    }
}
</script>

<style lang="scss" scoped>
.info-wrapper {
  width: calc(100% / 4 - 10px);
  height: 350px;
  border: 1px solid white;
  margin: 5px;

  .card {
    padding: 1rem .8rem;

    img {
      width: 30px;
    }
  }
}
</style>