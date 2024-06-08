<template>
  <div :class="`card flex items-center justify-center gap-5 rounded-3xl text-black`">

    <div class="flex">
      <LargeImage class="" :url="props.img"></LargeImage>
    </div>
    <div class="text flex flex-col  gap-16  pl-10">
      <div class="flex gap float-right">
        <Tag></Tag>
      </div>
      <h2 class="font weight bold">{{ props.name }}</h2>

      <div class="mono text-primary">
        24/04/23
      </div>

      <p class="w-96">
            Establece y expande tus propios asentamientos, libera la tierra y ayuda a sus aldeanos.
            Recluta a otros para tu causa mientras aprendes más sobre la vida que tuviste que dejar atrás.
            Dirige a tus fuerzas, demuestra tu valor en el combate y consolida tu lugar como el héroe de tu pueblo.
        </p>

        <div class="downBottoms flex gap-5 items-center">
        <Button :color="'primary'" @click="sumarItems()">13,95€</Button>
        <Button :icon="'shop'" @click="sumarItems()"> </Button>
        <Button :icon="'like'"></Button>
      </div>

    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";

// Inyectar la variable global
const itemsInCart = inject('itemsInCart')

const props = defineProps({
  name: String,
  img: String, 
  price: String,
});

let price = "";
price = props.price;
if (price == "" || price == undefined) {
  price = "13.95";
}
const sumarItems = () =>{
  itemsInCart.value.push(props.name)
  console.log(itemsInCart.value)
  console.log('hola')

}

</script>

<style lang="sass" scoped></style>