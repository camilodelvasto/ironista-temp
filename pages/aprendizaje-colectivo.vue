<template>
  <div class="index">
    <section class="statement" id="aprendizaje-colectivo">
      <div class="container">
        <div class="font-text">
          <div class="statement-body">Nuestro punto de partida es la esperanza y la convicción de que podemos ser mejores juntos a través del </div>
          <nuxt-link to="/aprendizaje-colectivo" class="statement-emphasis">aprendizaje colectivo.</nuxt-link>
        </div>
      </div>
    </section>

    <BlackFooter />
  </div><!--container-->
</template>

<script>
import BlackFooter from '~/components/BlackFooter.vue'

export default {
  transition: 'page',
  components: {
    BlackFooter
  }
}
</script>

<style scoped lang="scss">

.statement {
  margin-top: 40px;
}

.subtitle {
  font-size: 30px;
  padding-top: 20px;
  display: block;
  text-align: right;
}

.hero.is-primary {
  background-color: transparent;
  background-size: cover;
}

</style>
