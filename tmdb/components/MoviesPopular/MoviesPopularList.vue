<template>
    <div class="grid sm:grid-cols-1 md:grid-cols-5 md:gap-x-8 md:gap-y-8" v-if="listMoviesPopular.length">
        <MoviesPopularItemVue v-for="listMoviePopular in listMoviesPopular" :listMoviePopular="listMoviePopular" :key="listMoviePopular.id"/>
    </div>
</template>
<script>
import MoviesPopularItemVue from "./MoviesPopularItem.vue"
export default {
    components: {
        MoviesPopularItemVue
    },
    props: {
        listMoviesPopular: Array
    },
    
}
</script>