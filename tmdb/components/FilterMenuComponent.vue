<template>
    <div class="border-2 rounded-md grid grid-cols-1 divide-y">
        <div @click="closechevron()" class="grid grid-cols-2 gap-2 pl-4 pr-4 h-12">
            <div class="pt-3 font-medium text-base">
                <p>Filtrer</p>
            </div>
            <div class="pt-3 text-base">
                <svg
                    id="openchevron1"
                    style="float: right;"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5 isclick"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    stroke-width="2"
                >
                    <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
                </svg>
                <svg
                    id="closechevron1"
                    style="float:right;"
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-4 w-4 isnotclick"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    stroke-width="2"
                >
                    <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
                </svg>
            </div>
        </div>
        <div class="grid grid-cols-1 divide-y">
            <div id="divFilter" class="pb-5 hidden pt-3 pl-6 pr-5">
                <p class="mb-3 text-gray-400">Afficher</p>
                <div class="relative inline-flex align-middle w-full">
                    <div class="flex justify-center">
                        <div>
                            <div class="form-check">
                                <input class="form-radio appearance-none rounded-full h-4 w-4 border border-gray-300 bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2" type="radio" name="flexRadioDisabled" id="flexRadio" checked>
                                <label class="form-check-label inline-bloc" for="flexRadio">
                                    Tous
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-radio appearance-none rounded-full h-4 w-4 border border-gray-300 bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2" type="radio" name="flexRadioDisabled" id="flexRadio1">
                                <label class="form-check-label inline-block" for="flexRadio1">
                                    Films que je n'ai jamais vus 
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-radio appearance-none rounded-full h-4 w-4 border border-gray-300 bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2" type="radio" name="flexRadioDisabled" id="flexRadio2">
                                <label class="form-check-label inline-block" for="flexRadio2">
                                    Films que j'ai déjà vus 
                                </label>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div id="divFilter1" class="pb-5 hidden pt-3 pl-6 pr-5">
                <p class="mb-3 text-gray-400">Disponibilités</p>
                <div class="relative inline-flex align-middle w-full">
                    <div class="flex justify-center">
                        <div>
                            <input type="checkbox" class="form-checkbox h-4 w-4 border border-gray-300 bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2" checked>
                            <label>Rechercher parmi toutes les disponibilités?</label>
                        </div>
                    </div>
                </div>
            </div>
            <div id="divFilter2" class="pb-5 hidden pt-3 pl-6 pr-5">
                <p class="mb-3 text-gray-400">Date de sorties</p>
                <div class="relative inline-flex align-middle w-full">
                    <div class="grid grid-flow-row-dense grid-cols-2 grid-rows-2">
                        <div>
                            <p>Du</p>
                        </div>
                        <div>
                            <div class="flex items-center justify-center">
                                <div class="flex items-center justify-center">
                                    <div class="relative">
                                        <input datepicker type="date" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="-mt-4 relative inline-flex align-middle w-full">
                    <div class="grid grid-flow-row-dense grid-cols-2 grid-rows-2">
                        <div>
                            <p>au</p>
                        </div>
                        <div>
                            <div class="flex items-center justify-center">
                                <div class="flex items-center justify-center">
                                    <div class="relative">
                                        <input datepicker type="date" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
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
        </div>
    </div>
</template>

<script>

import { createPopper } from "@popperjs/core";

export default {
    name: "dropdown",
    data() {
        return {
            dropdownPopoverShow: false
        }
    },
    methods: {
        toggleDropdown: function () {
            if (this.dropdownPopoverShow) {
                this.dropdownPopoverShow = false;
            } else {
                this.dropdownPopoverShow = true;
                createPopper(this.$refs.btnDropdownRef, this.$refs.popoverDropdownRef, {
                    placement: "bottom-start"
                });
            }
        },
        closechevron: function () {

            var chevronright = document.getElementById('openchevron1')
            var chevronbottom = document.getElementById('closechevron1')
            var divFilter = document.getElementById('divFilter')
            var divFilter1 = document.getElementById('divFilter1')
            var divFilter2 = document.getElementById('divFilter2')
            var divFilter3 = document.getElementById('divFilter3')
            

            if (chevronright.classList.contains('isclick')) {
                chevronright.classList.remove('isclick')
                chevronright.classList.add('isnotclick')
                chevronbottom.classList.remove('isnotclick')
                chevronbottom.classList.add('isclick')
                divFilter.classList.remove('hidden')
                divFilter1.classList.remove('hidden')
                divFilter2.classList.remove('hidden')
                divFilter3.classList.remove('hidden')


            } else if (chevronbottom.classList.contains('isnotclick')) {
                chevronbottom.classList.remove('isclick')
                chevronbottom.classList.add('isnotclick')
                chevronright.classList.remove('isnotclick')
                chevronright.classList.add('isclick')
                divFilter.classList.add('hidden')
                divFilter1.classList.add('hidden')
                divFilter2.classList.add('hidden')
                divFilter3.classList.add('hidden')

            } else if (chevronbottom.classList.contains('isclick')) {
                chevronbottom.classList.remove('isclick')
                chevronbottom.classList.add('isnotclick')
                chevronright.classList.remove('isnotclick')
                chevronright.classList.add('isclick')
                divFilter.classList.add('hidden')
                divFilter1.classList.add('hidden')
                divFilter2.classList.add('hidden')
                divFilter3.classList.add('hidden')
            }
        },
    }
}
</script>