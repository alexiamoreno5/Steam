<template>
    <div class="flex flex-col gap-4 items-center">
        <p class="mono mini">
            3,200 alumnos
        </p>

        <SquareImg :url="props.img" class="rounded-full border-black w-40"></SquareImg>
        <h3><slot/></h3>
    </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";
const props = defineProps({
    img: String,
})
</script>

<style lang="sass" scoped></style>
