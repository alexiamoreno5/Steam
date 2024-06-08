<template>
  <div :class="`card flex gap-5 p-6  rounded-3xl bg-g800 text-white`">

    <div class="flex flex-col w-[40%]">
      <SquareImg class="" :url="props.img"></SquareImg>
      <div class="flex gap">
        <Tag></Tag>
        <Tag></Tag>
      </div>
    </div>
    <div class="text flex flex-col gap-16 w-[700px]">
      <h4>{{ props.name }}</h4>

      <div class="mono text-primary">
        24/04/23
      </div>
      <p>
        <slot></slot>
      </p>

    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";



const props = defineProps({
  name: String,
  img: String,
});




</script>

<style lang="sass" scoped></style>
