<template>
  <div :class="`card flex flex-col gap-5 ${textColor} p-6 rounded-3xl ${background} `">
   
    
    <div class="text flex flex-col gap-16">
      <h4>{{ props.name }}</h4>
      <p class="text-primary mono">1200 personas</p>
      <p class=" w-96">
        <slot></slot>
      </p>
      <div class="downBottoms flex gap-5 items-center">
        <Button :color="'primary'" >Participar</Button>
        
      </div>
    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";

import { inject } from 'vue'

// Inyectar la variable global
const itemsInCart = inject('itemsInCart')

const props = defineProps({
  color: String,
  name: String,
  
});

const sumarItems = () => {
  itemsInCart.value.push(props.name)
  console.log(itemsInCart.value)
  console.log('hola')

}


let background = "";
let textColor = "";
if (props.color == "dark") {
  background = "bg-g800";
  textColor = "text-white";
} else if (props.color == "light") {
  background = "bg-g100 box-border border-2 border-black";
  textColor = "text-black";
}
</script>

<style lang="sass" scoped></style>
