<template>
    <div class="max-w-sm relative rounded overflow-hidden shadow-lg">
        <img class="md:w-full" :src="'https://image.tmdb.org/t/p/w500'+listMoviePopular.poster_path" :alt="listMoviePopular.title">
        <div class="px-6 py-4">
            <div class="font-bold text-base mb-2">{{ listMoviePopular.title }}</div>
            <p class="text-gray-700 text-base">
            
            </p>
        </div>
        <div x-data="valeurProgress" class="absolute top-0 mt-56 left-0 ml-4 rounded-full inline-flex items-center justify-center overflow-hidden bg-black">
            <!-- <div x-data="scrollProgress" class="absolute inline-flex items-center justify-center overflow-hidden rounded-full"> -->
                <!-- Building a Progress Ring: https://css-tricks.com/building-progress-ring-quickly/ -->
                <svg class="w-10 h-10">
                    <circle class="text-gray-300" stroke-width="4" stroke="currentColor" fill="transparent" r="20" cx="20" cy="20"/>
                    <circle class="text-green-500" stroke-width="4" :stroke-dasharray="circumference" :stroke-dashoffset="circumference - percent / 100 * circumference" stroke-linecap="round" stroke="currentColor" fill="transparent" r="20" cx="20" cy="20" />
                </svg>
                <span class="absolute text-xl text-blue-700" x-text="`${listMoviePopular.vote_average * 100}%`"></span>
            <!-- </div> -->
        </div>
        <div class="absolute top-0 mt-3 right-0 mr-2 border h-6 w-6 rounded-full bg-white">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z" />
            </svg>
        </div>
    </div>
</template>
<script>
    export default {
        props: {
            listMoviePopular: Object
        },
        methods: {
            valeurProgress () {
                return {
                    init () {
                        this.percent = Math.round(this.$props.listMoviePopular.vote_average * 100)
                    },
                    circumference: 20 * 2 * Math.PI,
                }
                console.log(this.$props.listMoviePopular.vote_average)
            }
        }
    }
</script>