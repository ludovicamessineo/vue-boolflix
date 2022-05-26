<template>
  <li class="info-wrapper">
    <div class="card">
      <div class="front">
        <img :src=" `https://image.tmdb.org/t/p/w342/${showObj.poster_path}` " alt="">
      </div>

      <div class="back">
        <h2>{{ showObj.title ? showObj.title : showObj.name }}</h2>
        <h4>{{ showObj.original_title ? showObj.original_title : showObj.original_name }}</h4>
        <img v-if="addLangImg()" :src="require(`../assets/${showObj.original_language}.png`)" alt="">
        <p v-else> {{ showObj.original_language }} </p>
        <p>{{ showObj.vote_average}}</p>
        <p>
          <i v-for="n in 5" :key="n"
            class="fa-star"
            :class="n <= voteStars ? 'fas' : 'far' "></i>
        </p>
      </div>
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
    computed: {
      voteStars() {
        return Math.ceil(this.showObj.vote_average / 2)
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
@import '~@fortawesome/fontawesome-free/css/all.min.css';

.info-wrapper {
  width: calc(100% / 4 - 10px);
  height: 400px;
  margin: 5px;
  perspective: 1000px;


  .card {
    width: 100%;
    height: 100%;
    position: relative;
    background-color: black;
    transform-style: preserve-3d;
    transition: transform .9s;

    .front,
    .back {
      width: 100%;
      height: 100%;
      position: absolute;
      backface-visibility: hidden;
    }

    .back {
      padding: 1rem;
      transform: rotateY(180deg);
    }

    .front > img {
      width: 100%;
      padding: 0;
    }

    .back > img {
      width: 30px;
      padding: .3rem 0;
    }
  }
}

.info-wrapper:hover > .card {
  transform: rotateY(180deg);
}
</style>