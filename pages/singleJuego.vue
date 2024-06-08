<template>
    <title>Juego</title>
    <div class="flex flex-col gap-8 p-20 bg-g100 ">

        <div class="flex flex-col items-center">
            <CardGameLarge class="max-w-[800px]" :img="arrayJuegos[0].img" :name="`${arrayJuegos[0].name}`">
                Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos.
                Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás.
                Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.
            </CardGameLarge>
        </div>

        <div class="flex flex-col items-center">
            <MiniCarousel></MiniCarousel>
        </div>

        <div class="flex flex-col gap-12 overflow-x-scroll scrollbar">
            <h1 class="text-black">
                Comentarios
            </h1>
            <div class="flex gap-12">
                <!-- /////////////// -->
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>

                <CardComentario></CardComentario>
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>
                <CardComentario></CardComentario>



                <!-- gggggggggggggggggggg -->
            </div>
        </div>
        <div class="flex flex-col gap-12">
            <h1 class="text-black">
                Juegos relacionados
            </h1>
            <div class="flex gap-12 overflow-x-scroll scrollbar">
                <!-- gggggggggggggggggggg -->
                <CardJuego v-for="i in arrayJuegos" :img="i.img" :name="i.name"></CardJuego>



                <!-- gggggggggggggggggggg -->
            </div>
        </div>
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