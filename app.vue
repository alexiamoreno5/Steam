<template>
  <div>
    <NavBar :shop="navBarShop" :primary="navBarPrimary" :logged="navBarLogged" class="sticky top-0 z-50"></NavBar>
    <NuxtPage />
    <Footer />
  </div>
</template>

<script setup>
import { ref, watch, provide } from 'vue'
import { useRoute } from 'vue-router'

const navBarPrimary = ref('')
const navBarLogged = ref(false)
const navBarShop = ref(false)

const itemsInCart = ref([])
const arrayJuegos = ref([
  {
    img: '/arrayJuegos/1.jpg',
    name: 'Contra 1'
  }
])

async function fetchGames() {
  const url = 'https://api.rawg.io/api/games?key=aaf4c3895112423396836433741c6d2f&dates=2019-09-01,2019-09-30&platforms=18,1,7'
  
  try {
    const response = await fetch(url)
    if (!response.ok) {
      throw new Error('Error en la respuesta de la API')
    }

    const data = await response.json()

    for (const game of data.results) {
      if (game.name && game.background_image) {
        arrayJuegos.value.push({
          img: game.background_image,
          name: game.name
        })
      }
    }

  } catch (error) {
    console.error('Error al hacer el fetch a la API:', error)
  }
}

fetchGames()

provide('itemsInCart', itemsInCart)
provide('arrayJuegos', arrayJuegos)
provide('navBarLogged', navBarLogged)

const route = useRoute()

watch(route, (newRoute) => {
  if (newRoute.path.includes('comunidadAmigos')) {
    navBarShop.value = true
    
  } else if (newRoute.path.includes('comunidadDiscussion')) {
    navBarShop.value = true
    
  } else if (newRoute.path.includes('comunidadNoticias')) {
    navBarShop.value = true
    
  } else if (newRoute.path.includes('comunidadStream')) {
    navBarShop.value = true
    
  } else if (newRoute.path.includes('comunidadVideo')) {
    
    navBarShop.value = true
  }
  else if (newRoute.path.includes('comunidadMentores')) {
    
    navBarShop.value = true
  } else {
    navBarPrimary.value = ''
    navBarShop.value = false
  }
}, { immediate: true })








</script>


<style lang="sass">

</style>


