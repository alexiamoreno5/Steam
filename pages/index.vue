<template>
    <title>Tienda de Juegos</title>
    <div class="flex flex-col relative">

        <div class="flex flex-col gap-8">
            <section class="flex relative bgimage w-full h-[70vh] rounded-3xl mb-11">
                <CardJuegoDestacado :name="'Camera Games'" class="absolute top-10 left-10">
                    ¡Mejor juego elegido del mes! Cómpratelo ya, mola que flipas, lo juega mi hermana, sino te lo compras
                    te arrepentirás toda tu vida. Aprovecha ahora que está de oferta hasta la semana que viene. 
                </CardJuegoDestacado>
            </section>
            <div class="flex justify-center">
                <CardNoticia :img="arrayJuegos[0].img" :name="arrayJuegos[0].name" class="w-[70%]">
                    Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos.
                    Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás.
                    Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.</CardNoticia>
            </div>
            <div class="scroll-container ">
                <div class="flex gap-10 p-10 overflow-x-scroll scrollbar">
                    <CardJuegoMes v-for="i in arrayJuegos" :color="'dark'" :name="i.name" :img="i.img">
                        Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos.
                        Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás.
                        Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.
                    </CardJuegoMes>
                </div>
            </div>


        </div>
        <!-- <Footer></Footer> -->
       


    </div>
</template>


<script setup>
import { ref } from 'vue';
import { inject } from 'vue'
import CardJuegoMes from '~/components/CardJuegoMes.vue';

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