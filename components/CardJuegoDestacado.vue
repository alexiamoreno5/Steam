<template>
  <div
    class="card flex flex-col gap-6 px-16 py-8 bg-g800 rounded-[35px] bg-opacity-70 w-[655px]">
  <NuxtLink to="/singleJuego"><h1 class="text-white">{{ props.name }}</h1></NuxtLink>
    <p class="text-g400 pb-10">
      <slot></slot>
    </p>
    <div class="downButtons flex gap-5 items-center">
      <Button :color="'primary'">13,95€</Button>
      <Button :icon="'like'"></Button>
    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";

const props = defineProps({
  name: String,
});
</script>

<style lang="sass" scoped></style>
