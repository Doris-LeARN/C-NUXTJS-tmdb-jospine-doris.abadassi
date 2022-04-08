<template>
   <div>
       <a href="#" class="text-xs rounded-full border-2 mb-3 px-4 py-1">{{ listGenre.name }}</a>
   </div>
</template>
<script>
export default {
    props: {
        listGenre: Object
    }
}
</script>