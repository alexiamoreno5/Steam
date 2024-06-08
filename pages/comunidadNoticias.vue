<template>
    <title>Noticias</title>
    <div class="flex gap-8 p-20 bg-g300 overflow-x-scroll scrollbar">

        <CardNoticia v-for="i in arrayJuegos" :img="i.img" :name="i.name" class="w-[70%]"> I have a dashboard
            with
            two sides, a nav on the left and the main content on the right, simple. They
            both are housed by a main div which has the height of the current screen. I need the main content
            div to scroll internall
        </CardNoticia>
   


    </div>
</template>



<script setup>
import { ref } from 'vue';
import { inject } from 'vue'

// Inyectar la variable global
const arrayJuegos = inject('arrayJuegos')

let dropdown = ref(false)
const dropdownModal = () => {
    dropdown.value = !dropdown.value
}

</script>


<style lang="sass" scoped>

 .bgimage
    background-image: url('sampleimg.jpg')
    background-size: cover
    background-position: center

.scrollbar
    scrollbar-width: thin
    scrollbar-color: black white

</style>