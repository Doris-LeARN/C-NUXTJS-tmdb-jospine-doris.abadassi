<template>
    <div class="border max-h-max md:container md:mx-auto pt-10">
        <h2 class="text-2xl">Films populaires</h2>
        <div class="mt-8 grid grid-flow-row-dense grid-cols-4 grid-rows-3 gap-4">
            <div>
                <SortMenuComponent class="mb-5"/>
                <FilterMenuComponentVue />
            </div>
            <div class="col-span-3 border border-red-700 pt-10 h-64">
                <div class="grid grid-cols-5 gap-x-2 gap-y-2">
                    
                </div>
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
import FilterMenuComponentVue from "./FilterMenuComponent.vue";
export default {  
    components: {
        SortMenuComponent,
        FilterMenuComponentVue
    },
    data() {
        return {
            dropdownPopoverShow: false,
            listGenres: []
        }
    },
    beforeMount () {
        this.getListGenres()
    },
    methods:{
        
        async getListGenres () {
            const res = await fetch('https://api.themoviedb.org/3/genre/movie/list?api_key=b1d7d44c6fcbba479ced84ce5a1b6426&language=en-US') 
            const data = await res.json()
            this.listGenres = data
            console.log(this.listGenres)
        }
    }
    
}
</script>
