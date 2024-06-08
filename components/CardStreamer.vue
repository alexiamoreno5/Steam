<template>
    <div :class="`flex rounded-full items-center ${bg} ${text} px-16 py-11 justify-between`">
        <div class="flex gap-10 items-center">
            <h3>
                Streamer
            </h3>
            <p class="mono text-primary">
                1,234 people
            </p>
            <p class="w-[60%]">
                De ese modo, todo texto contiene una serie de mensajes cifrados que el lector debe poder recuperar, y
                que
                puede ser de diversa índole, conforme a los cometidos expresivos de quien lo redactó: son textos las
                instrucciones de uso de una lavadora, pero también un poema de amor, las noticias del diario o un
                grafiti de
                protesta en una pared en la calle.
            </p>
        </div>
    <NuxtLink to="/comunidadVideo">
       <div class="flex gap-5 items-center">
            <Button :color="'primary'">Participar</Button>
            <Button :icon="'like'"></Button>
       </div>
    </NuxtLink>

    </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";

const props = defineProps({
    color: String,
})

let bg = ref('bg-g800')
let text = ref('text-black')

if (props.color == 'dark') {
    bg.value = 'bg-g800'
    text.value = 'text-white'

}
if (props.color == 'light') {
    bg.value = 'bg-g100'
    text.value = 'text-black'
}


</script>

<style lang="sass" scoped>

</style>
