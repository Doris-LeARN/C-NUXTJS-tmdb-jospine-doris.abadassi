<template>
  <div>
    <TheHeader />
    <nuxt />
    <MoviesMain />
  </div>
</template>
<script>
import TheHeader from "../components/TheHeader.vue";
import MoviesMain from "../components/MoviesMain.vue";
export default {
  components: {
    TheHeader,
    MoviesMain
  },
  /*data: () => ({
    listGenres: []
  }),
  beforeMount () {
    this.getListGenres()
  },
  methods: {
    async getListGenres () {
      const res = await fetch('https://api.themoviedb.org/3/genre/movie/list?api_key=b1d7d44c6fcbba479ced84ce5a1b6426&language=en-US') 
      const data = await res.json()
      this.listGenres = data
      console.log(this.listGenres)
    }
  }*/
}
</script>

<style>
  body {
    font-family: 'Arial, sans-serif';
  }
</style>