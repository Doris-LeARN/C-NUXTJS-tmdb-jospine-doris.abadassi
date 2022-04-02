<template>
    <div id="divFilter3" class="pb-5 hidden pt-3 pl-6 pr-5">
                <p class="mb-3 text-gray-400">Genres</p>
                <div class="grid grid-cols-2 mb-4">
                    <!--<div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Action</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Animation</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Aventure</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Comédie</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Crime</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Documentaire</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Drame</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Familial</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Fantastique</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Guerre</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Histoire</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Horreur</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Musique</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Mystère</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Romance</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Science-Fiction</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Thriller</a><!--</div>
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Téléfilm</a><!--</div>
                </div>
                <div class="grid grid-cols-2 mb-4">
                    <div>--><a href="#" class="text-xs rounded-full border-2 px-4 py-1">Western</a><!--</div>-->
                </div>
            </div>
</template>
<script>
export default {
    data () {
        return {
            listGenres
        }
    },
    beforeMount () {
        this.getListGenres()
    },
    methods: {
        async getListGenres () {
            this.listGenres = await this.$axios.$get('https://api.themoviedb.org/3/genre/movie/list?api_key=b1d7d44c6fcbba479ced84ce5a1b6426&language=en-US')
            console.log(this.listGenres)
        }
    }
}
</script>