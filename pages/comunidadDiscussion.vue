<template>
    <title>Discusiones</title>
    <div class="flex gap-8 p-20 overflow-x-scroll scrollbar">


        <CardTema v-for="i in arrayJuegos" :name="'Tema'" :color="'dark'">
            Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos.
            Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás.
            Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.
        </CardTema>
      
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