<template>
  <div class="index">
    <section class="statement" id="aprendizaje-intro">
      <div class="container">
        <div class="font-text">
          <div class="statement-body">Nuestro punto de partida es la esperanza y la convicción de que podemos ser mejores juntos a través del </div>
          <nuxt-link to="/aprendizaje-colectivo" class="statement-emphasis">aprendizaje colectivo.</nuxt-link>
        </div>
      </div>
    </section>
  </div><!--container-->
</template>

<script>
export default {
  transition: 'page',
  data () {
    return {
      statement: {
        main: 'Para un ironista el camino para cambiarnos como sociedad es la redescripción.',
        sub: 'No se trata de descubrir la fórmula para cambiar el mundo, sino de imaginar una nueva forma de describirnos como sociedad.'
      },
      image: require('~/assets/img/street-art-graffiti.jpg')
    }
  }
}
</script>

<style scoped lang="scss">
.title-wrapper {

  @include breakpoint($sm) {
    text-align: right;
  }

  .title {
    font-size: 40px;
    background: rgba($color-emphasis,0.7);
    display: inline;
    line-height: 1.38;

    @include breakpoint($sm) {
      font-size: 55px;
    }
  }
}

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
