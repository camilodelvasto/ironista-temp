<template>
  <div class="index how">
    <section class="statement hero is-fullheight">
      <div class="hero-body">
        <div class="container">
          <div class="statement-large">
            <span class="st-1">El primer paso para transformar es comprender. Porque nuevas comprensiones son en sí mismas grandes transformaciones. Por eso nuestro proceso inicia siempre por una profunda comprensión de las creencias, expectativas, explicaciones y juegos de lenguaje de los grupos sociales. A partir de una comprensión renovada iniciamos procesos de aprendizaje colectivo mediante el juego, el liderazgo comunicativo y la comunicación intensificada.</span>
            <nuxt-link to="/contacto">Conozca más de lo que hacemos.</nuxt-link>
          </div>
        </div>
      </div>
    </section>
  </div><!--container-->
</template>

<script>
import { TweenMax, Back } from 'gsap'

export default {
  transition: {
    mode: 'out-in',
    css: false,
    beforeEnter (el) {
      TweenMax.set(el, {
        transformPerspective: 100,
        perspective: 300,
        transformStyle: 'preserve-3d'
      })
    },
    enter (el, done) {
      TweenMax.to(el, 1, {
        rotationY: 360,
        transformOrigin: '50% 50%',
        ease: Back.easeOut
      })
      done()
    },
    leave (el, done) {
      TweenMax.to(el, 1, {
        rotationY: 0,
        transformOrigin: '50% 50%',
        ease: Back.easeIn
      })
      done()
    }
  }
}
</script>

<style scoped lang="scss">
  .st-1 {
    margin-bottom: 30px;
    display: block;
  }

</style>
