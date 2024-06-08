<template>
    <title>Soporte</title>
     <div class="flex flex-col gap-20">
      <div class="flex flex-col gap-10 items-center">
            <h1>
              ¿Con qué necesitas ayuda?
            </h1>
            <div class="flex gap-6">
              <div class="flex bg-g400 rounded-full gap-2 items-center justify-center px-12">

                <p class="mono underline">
                  Search...
                </p>
                <Button :icon="'search'" :littleIcon="true"></Button>

              </div>
              <Button :color="'primary'">Contáctanos</Button>
            </div>
      </div>
      <div class="flex gap-8 justify-start border-t-2 border-b-2 border-black mx-60 p-10">
        <img src="/sampleimg.jpg" alt="" class="rounded-3xl w-[400px] object-cover">
        <div class="flex flex-col justify-between gap-10">
          <h2>
            INICIO DE SESIÓN
          </h2>
          <div class="flex flex-col gap-6">
            <h4 class="bold">
            He olvidado mi contraseña.
          </h4>
          <h4 class="bold">
            No he recibido el email para confirmar la cuenta.
          </h4>
          <h4 class="bold">
            Mi cuenta de correo ya no existe.
          </h4>
          </div>

        </div>
      </div>
      <!-- ///////////////////////////////////////////////////// -->


        <div class="flex flex-col gap-6 p-20">
          <h2>
            JUEGOS
          </h2>
          <div class="flex overflow-x-scroll scrollbar gap-10">
            <CardJuego v-for="i in arrayJuegos" :img="i.img" :name="i.name"></CardJuego>
          </div>
          <div class="flex overflow-x-scroll scrollbar gap-10">
            <CardJuego v-for="i in arrayJuegos" :img="i.img" :name="i.name"></CardJuego>
          </div>
        </div>



      <!-- ///////////////////////////////////////////////////// -->
      <div class="flex gap-8 justify-start border-t-2 border-b-2 border-black mx-60 p-10">
        <img src="/sampleimg.jpg" alt="" class="rounded-3xl w-[400px] object-cover">
        <div class="flex flex-col justify-between gap-10">
          <h2>
            COMPRAS
          </h2>
          <div class="flex flex-col gap-6">
            <h4 class="bold">
            ¿Cómo puedo obtener un recibo por mi cuenta?
          </h4>
          <h4 class="bold">
            ¿Qué formas de pago puedo utilizar para realizar una compra?
          </h4>
          <h4 class="bold">
            ¿Puedo pagar con bitcoin?
          </h4>
          </div>

        </div>
      </div>
      <div class="flex gap-8 justify-start border-t-2 border-b-2 border-black mx-60 p-10">
        <img src="/sampleimg.jpg" alt="" class="rounded-3xl w-[400px] object-cover">
        <div class="flex flex-col justify-between gap-10">
          <h2>
            MI CUENTA 
          </h2>
          <div class="flex flex-col gap-6">
            <h4 class="bold">
            ¿Cómo cambio el pais en mi cuenta?
          </h4>
          <h4 class="bold">
            ¿Cómo cambiar el nombre de vista al público?
          </h4>
          <h4 class="bold">
            ¿Cómo cambiar mi username?
          </h4>
          </div>

        </div>
      </div>
     </div>
    
    
  
  </template>
  

  
  <script setup>
  import { ref } from 'vue';
  import SquareImg from '~/components/SquareImg.vue';
  import Button from '~/components/mockComponents/Button.vue';
  import LoginModal from '~/components/LoginModal.vue';
  import { inject } from 'vue'

// Inyectar la variable global
const arrayJuegos = inject('arrayJuegos')
  
  let loginModal = ref(false);
  let filtro = false
  
  const seeModal = () => {
    loginModal.value = !loginModal.value;
  };
  </script>

<style lang="sass" scoped>

.k
    @apply bg-transparent text-black p-6
    box-shadow: inset 0px 0px 0px 8px black
    box-sizing: border-box
.k:hover
    @apply bg-primary text-black p-6
    box-shadow: inset 0px 0px 0px 4px black
    box-sizing: border-box

.scrollbar
    scrollbar-width: thin
    scrollbar-color: black white

</style>
