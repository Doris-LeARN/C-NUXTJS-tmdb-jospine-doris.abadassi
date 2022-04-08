<template>
    <div class="max-w-sm relative rounded overflow-hidden shadow-lg">
        <img class="md:w-full" :src="'https://image.tmdb.org/t/p/w500'+listMoviePopular.poster_path" :alt="listMoviePopular.title">
        <div class="px-6 py-4">
            <div class="font-bold text-sm mb-2">{{ listMoviePopular.title }}</div>
            <p class="text-gray-700 text-base">
            
            </p>
        </div>
        <div class="absolute top-0 mt-56 left-0 ml-4 rounded-full inline-flex items-center justify-center overflow-hidden bg-black">
            <ProgressRing :radius="20" :progress="progress" :stroke="2" />
            <span class="absolute text-sm text-white">{{ Math.round(this.$props.listMoviePopular.vote_average * 100)/10 }}</span>
            <span id="percent" class="absolute text-sm text-white">%</span>
        </div>
        <button class="absolute top-0 mt-3 right-0 mr-2 h-5 w-5 opacity-50 rounded-full bg-white hover:bg-blue-400 hover:opacity-100" type="button" v-on:click="toggleDropdownBtn()" ref="btnDropdownBtnRef">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z" />
            </svg>
        </button>
        <div v-bind:class="{ 'hidden': !dropdownPopoverShow, 'block': dropdownPopoverShow }" id="dropdownDivider" class="z-10 w-44 bg-white rounded divide-y divide-gray-600 shadow dark:bg-gray-700 dark:divide-gray-600" ref="popoverDropdownItemRef">
            <div class="py-1">
            <a href="#" class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 dark:text-gray-200 dark:hover:text-white">Separated link</a>
            </div>
            <div class="py-1">
            <a href="#" class="block py-2 px-4 text-sm text-gray-700 hover:bg-gray-100 dark:hover:bg-gray-600 dark:text-gray-200 dark:hover:text-white">Separated link</a>
            </div>
        </div>
    </div>
</template>
<style>
    #percent {
        font-size: 0.5rem;
        top: 9px;
        right: 6px;
    }
</style>
<script>
import { createPopper } from "@popperjs/core"
import ProgressRing from "./ProgressRing.vue"
    export default {
        components: {
            ProgressRing
        },
        data(){
            return {
                progress: 0,
                dropdownPopoverShow: false
            }
        },
        props: {
            listMoviePopular: Object
        },
        mounted() {
            // emulating progress
            const interval = setInterval(() => {
            this.progress += 1;
            if (this.progress === Math.round(this.$props.listMoviePopular.vote_average * 100)/10)
                clearInterval(interval);
            }, 1000);
            console.log(Math.round(this.$props.listMoviePopular.vote_average * 100)/10)
        },
        methods: {
            toggleDropdownBtn: function () {
                if (this.dropdownPopoverShow) {
                    this.dropdownPopoverShow = false;
                } else {
                    this.dropdownPopoverShow = true;
                    createPopper(this.$refs.btnDropdownBtnRef, this.$refs.popoverDropdownItemRef, {
                        placement: "bottom-start"
                    });
                }
            }
        }
    }
</script>