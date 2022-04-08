<template>
    <div class="border-2 rounded-md grid grid-cols-1 divide-y">
        <div @click="closechevron()" class="grid grid-cols-2 gap-2 pl-4 pr-4 h-12">
            <div class="pt-3 font-medium text-base">
                <p>Trier</p>
            </div>
            <div class="pt-3 text-base">
                <svg
                    id="openchevron"
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
                    id="closechevron"
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
        <div id="divSort" class="pb-5 hidden pt-3 pl-6 pr-5">
            <p class="mb-3 text-gray-400">Trier les résultats par</p>
            <div class="relative inline-flex align-middle w-full">
                <button
                    class="dropdown-toggle px-5 py-2.5 p-3 bg-gray-200 text-gray-700 font-medium text-xs leading-tight rounded shadow-md hover:bg-gray-300 hover:shadow-lg focus:bg-gray-300 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-gray-400 active:shadow-lg active:text-white transition duration-150 ease-in-out flex items-center whitespace-nowrap"
                    type="button"
                    v-on:click="toggleDropdown()"
                    ref="btnDropdownRef"
                >
                    Popularité +/-
                    <svg
                        aria-hidden="true"
                        focusable="false"
                        data-prefix="fas"
                        data-icon="caret-down"
                        class="w-2 ml-32"
                        role="img"
                        xmlns="http://www.w3.org/2000/svg"
                        viewBox="0 0 320 512"
                    >
                        <path
                            fill="currentColor"
                            d="M31.3 192h257.3c17.8 0 26.7 21.5 14.1 34.1L174.1 354.8c-7.8 7.8-20.5 7.8-28.3 0L17.2 226.1C4.6 213.5 13.5 192 31.3 192z"
                        />
                    </svg>
                </button>
                <div
                    v-bind:class="{ 'hidden': !dropdownPopoverShow, 'block': dropdownPopoverShow }"
                    class="bg-white text-base z-50 float-left pl-4 pr-32 py-2 list-none text-left rounded shadow-lg mt-1"
                    ref="popoverDropdownRef"
                >
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Popularité +/-</a>
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Popularité -/+</a>
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Note +/-</a>
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Note -/+</a>
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Date de sortie +/-</a>
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Date de sortie -/+</a>
                    <a
                        class="text-sm py-2 font-normal block whitespace-nowrap bg-transparent text-gray-700 hover:bg-gray-100"
                        href="#"
                    >Titres (De A à Z)</a>
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

            var chevronright = document.getElementById('openchevron')
            var chevronbottom = document.getElementById('closechevron')
            var divSort = document.getElementById('divSort')

            if (chevronright.classList.contains('isclick')) {
                chevronright.classList.remove('isclick')
                chevronright.classList.add('isnotclick')
                chevronbottom.classList.remove('isnotclick')
                chevronbottom.classList.add('isclick')
                divSort.classList.remove('hidden')
            } else if (chevronbottom.classList.contains('isnotclick')) {
                chevronbottom.classList.remove('isclick')
                chevronbottom.classList.add('isnotclick')
                chevronright.classList.remove('isnotclick')
                chevronright.classList.add('isclick')
                divSort.classList.add('hidden')
            } else if (chevronbottom.classList.contains('isclick')) {
                chevronbottom.classList.remove('isclick')
                chevronbottom.classList.add('isnotclick')
                chevronright.classList.remove('isnotclick')
                chevronright.classList.add('isclick')
                divSort.classList.add('hidden')
            }
        },
    }
}
</script>