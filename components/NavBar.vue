<template>
  <div class="flex flex-col bg-white">
    <div class="flex justify-between px-12 py-6 items-center">
      <NuxtLink to="/"><img src="/steamLogo.svg" alt="logo" /></NuxtLink>
      <div class="flex gap-12 h-fit items-center">
        <Button :littleText="true" :color="'transparent'">Tienda</Button>

        <NuxtLink to="/comunidadNoticias">
            <Button :littleText="true" :color="'transparent'">Comunidad</Button>
        </NuxtLink>
        <NuxtLink to="/soporte">
        <Button :littleText="true" :color="'transparent'">Soporte</Button>
        </NuxtLink>
        <Button :icon="'community'" :littleIcon="true"></Button>
        <Button :littleText="true" :color="'gray'">Instala Steam</Button>

        <template v-if="props.logged == false">
          <NuxtLink to="/inicio">
            <Button :littleText="true" :color="'primary'">Inicia Sesión</Button>
          </NuxtLink>
        </template>
        <template v-if="props.logged ">
          <img src="/user.png" alt="" class="w-14">
        </template>

      </div>
    </div>
    <div v-if="shop" class="flex flex-col gap-7 p-12">
      <div class="flex justify-between">
        <h2>Comunidad</h2>
        <div class="flex gap-6">
          <Button :icon="'community'"></Button>
          <div class="flex relative">
            <NuxtLink to="/shoppingCart">
              <Button :icon="'cart'"></Button>
            </NuxtLink>
            <p v-if="itemsInCart.length > 0" class="flex justify-center items-center text-black bg-primary w-5 h-5 mono rounded-full absolute top-0 left-8">
              {{ itemsInCart.length }}
            </p>
          </div>
        </div>
      </div>
      <div class="flex gap-11">
        <NuxtLink to="/comunidadNoticias">
            <Button :littleText="true" :color="nuevos">
            Noticias
          </Button>
        </NuxtLink>

        <NuxtLink to="/comunidadDiscussion">
          <Button :littleText="true" :color="juegos">
            Discusiones
          </Button>
        </NuxtLink>

        <NuxtLink to="/comunidadStream">
          <Button :littleText="true" :color="ofertas">
            Streaming
          </Button>
        </NuxtLink>

        <NuxtLink to="/comunidadAmigos">
          <Button :littleText="true" :color="puntos">
            Amigos
          </Button>
        </NuxtLink>
        
        <NuxtLink to="/comunidadMentores">
          <Button :littleText="true" :color="puntos">
            Mentores
          </Button>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watchEffect } from 'vue';
import Button from "./mockComponents/Button.vue";
import { inject } from 'vue';


const itemsInCart = inject('itemsInCart');

const props = defineProps({
  shop: Boolean,
  primary: String,
  logged: Boolean
});

const nuevos = ref("");
const juegos = ref("");
const ofertas = ref("");
const puntos = ref("");

watchEffect(() => {
  if (props.primary === 'nuevos') {
    nuevos.value = "primary";
    juegos.value = "";
    ofertas.value = "";
    puntos.value = "";
  } else if (props.primary === 'juegos') {
    juegos.value = "primary";
    nuevos.value = "";
    ofertas.value = "";
    puntos.value = "";
  } else if (props.primary === 'ofertas') {
    ofertas.value = "primary";
    nuevos.value = "";
    juegos.value = "";
    puntos.value = "";
  } else if (props.primary === 'puntos') {
    puntos.value = "primary";
    nuevos.value = "";
    juegos.value = "";
    ofertas.value = "";
  } else {
    nuevos.value = "";
    juegos.value = "";
    ofertas.value = "";
    puntos.value = "";
  }
});
</script>

<style lang="sass" scoped></style>
