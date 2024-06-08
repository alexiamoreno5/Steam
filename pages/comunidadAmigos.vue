<template>
    <title>Amigos</title>
    <div class="flex gap-8 p-20 overflow-x-scroll scrollbar">
        <CardAmigo v-for="i in arrayJuegos" :img="i.img">Username</CardAmigo>
       
        
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