<template>
    <div class="border max-h-max md:container md:mx-auto pt-10">
        <h2 class="text-2xl">Films populaires</h2>
        <div class="mt-8 grid grid-flow-row-dense grid-cols-4 grid-rows-3 gap-4">
            <div>
                <SortMenuComponent class="mb-5"/>
                <FilterMenuComponentVue :listGenres='listGenres'/>
            </div>
            <div class="max-h-max col-span-3">
                <MoviesPopularListVue :listMoviesPopular='listMoviesPopular'/>
            </div>
        </div>
    </div>
</template>
<style>
    .isclick {
        display: block;
    }
    .isnotclick {
        display: none;
    }
    .showDivSort {
        display: block !important;
    }

</style>
<script>
import { createPopper } from "@popperjs/core";
import SortMenuComponent from "./SortMenuComponent.vue"
import FilterMenuComponentVue from "./RightButton/FilterMenuComponent.vue"
import MoviesPopularListVue from "./MoviesPopular/MoviesPopularList.vue";
export default {  
    components: {
        SortMenuComponent,
        FilterMenuComponentVue,
        MoviesPopularListVue
    },
    data: () => ({
        dropdownPopoverShow: false,
        listGenres: [],
        listMoviesPopular: []
    }),
    async beforeMount () {
        this.listGenres = await this.getListGenres(),
        this.listMoviesPopular = await this.getListMoviesPopular()
    },
    methods:{
        async getListGenres () {
            const res = await fetch('https://api.themoviedb.org/3/genre/movie/list?api_key=b1d7d44c6fcbba479ced84ce5a1b6426&language=en-US')
            const data = await res.json()
            this.listGenres = data.genres
            return this.listGenres
        },
        async getListMoviesPopular () {
            const res = await fetch('https://api.themoviedb.org/3/movie/popular?api_key=b1d7d44c6fcbba479ced84ce5a1b6426&language=en-US')
            const data = await res.json()
            this.listMoviesPopular = data.results
            console.log(this.listMoviesPopular)
            return this.listMoviesPopular
        }
    }
}
</script>
