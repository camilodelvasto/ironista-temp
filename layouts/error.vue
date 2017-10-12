<template>
  <div class="default-layout">
    <Navigation />
    <section class="statement">
      <div class="container">
        <div class="font-text">
          <h1 v-if="error.statusCode === 404">Página no encontrada</h1>
          <h1 v-else>Ocurrió un error</h1>
          <p>Ups, esta página no fue encontrada. Regresa al <nuxt-link to="/">inicio</nuxt-link>.</p>
        </div>
      </div>
    </section>

    <BlackFooter />
  </div>
</template>

<script>
import Navigation from '~/components/Navigation.vue'
import BlackFooter from '~/components/BlackFooter.vue'

export default {
  components: {
    Navigation,
    BlackFooter
  },
  props: ['error']
}
</script>

<style>
</style>