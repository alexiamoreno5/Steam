<template>
  <div class="flex flex-col bg-g200 gap-24 p-14">
    <div class="flex justify-between">
      <p class="text-primary">
        Para cualquier pregunta, por favor, contacta con steam@support.com
      </p>
      <div class="flex gap-6">
        <div class="flex flex-col gap-3">
          <NuxtLink to="/"><h5>Tienda</h5></NuxtLink>
          <NuxtLink to="/"><p>Nuevos y destacables</p></NuxtLink>
          <NuxtLink to="/"><p>Juegos por tipo</p></NuxtLink>
          <NuxtLink to="/"><p>Ofertas</p></NuxtLink>
          <NuxtLink to="/"><p>Tienda de puntos</p></NuxtLink>
        </div>
        <div class="flex flex-col gap-3">
          <NuxtLink to="/comunidadNoticias"><h5>Comunidad</h5></NuxtLink>
          <NuxtLink to="/comunidadNoticias"><p>Noticias</p></NuxtLink>
          <NuxtLink to="/comunidadDiscusiones"><p>Discusiones</p></NuxtLink>
          <NuxtLink to="/comunidadStream"><p>Streaming</p></NuxtLink>
          <NuxtLink to="/comunidadMentores"><p>Mentores</p></NuxtLink>
          <NuxtLink to="/comunidadAmigos"><p>Amigos</p></NuxtLink>
        </div>
        <div class="flex flex-col gap-3">
          <NuxtLink to="/soporte"><h5>Soporte</h5></NuxtLink>
          <NuxtLink to="/soporte"><p>Inicio de sesión</p></NuxtLink>
          <NuxtLink to="/soporte"><p>Juegos</p></NuxtLink>
          <NuxtLink to="/soporte"><p>Compras</p></NuxtLink>
          <NuxtLink to="/soporte"><p>Mis puntos</p></NuxtLink>
        </div>
      </div>
    </div>
    <div class="flex gap-3">
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
      <Button :icon="'community'" :littleIcon="true"></Button>
    </div>
    <div class="flex flex-col gap-16">
      <div class="flex justify-between">
        <p class="bold">Bread | Bread | Bread | Bread | Bread</p>
        <Button :icon="'community'" :littleIcon="true"></Button>
      </div>
      <div class="flex justify-between">
        <p>@2024 Steam. All rights reserved</p>
        <div class="flex">
          <p>Política y privacidad</p>
          <p>Términos y condiciones</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Tag from "./mockComponents/Tag.vue";
import Button from "./mockComponents/Button.vue";
</script>

<style lang="sass" scoped></style>
