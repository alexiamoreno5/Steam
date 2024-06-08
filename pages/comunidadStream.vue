<template>
    <title>Streaming</title>
    <div class="flex flex-col gap-8 p-20 bg-g300">

        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
        <CardStreamer :color="'light'"></CardStreamer>
        <CardStreamer :color="'dark'"></CardStreamer>
       

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