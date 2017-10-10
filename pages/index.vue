<template>
  <div class="index">
    <section class="hero is-primary is-medium"
      v-bind:style="{ backgroundImage: `url('${image}')` }"
    >
      <div class="hero-body">
        <div class="container">
          <div class="title-wrapper" v-for="(statement, index) in statements" >
            <transition name="fade">
              <h1 class="title" v-if="index === currentStatement % statements.length">
                <div v-html="statement"></div>
              </h1>
            </transition>
          </div>
        </div>
      </div>
    </section>

    <section class="statement">
      <div class="container">
        <div class="font-text">
          <h3>Nuestro punto de partida es la esperanza y la convicción de que podemos ser mejores juntos a través del </h3>
          <p>aprendizaje colectivo.</p>
          <nuxt-link to="/como-lo-hacemos"><button class="next slide">¿Cómo lo hacemos?</button></nuxt-link>
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
      statements: [
        '<span class="title-standard">Para un ironista el camino para cambiarnos como sociedad es la </span><span class="title-emphasis">redescripción.</span>',
        '<span class="title-standard">No se trata de descubrir la fórmula para cambiar el mundo, sino de </span><span class="title-emphasis">imaginar una nueva forma de describirnos </span><span class="title-standard">como sociedad.</span>'
      ],
      currentStatement: 0,
      timer: null,
      image: require('~/assets/img/street-art-graffiti.jpg')
    }
  },
  mounted () {
    this.startRotation()
  },
  methods: {
    startRotation: function () {
      this.timer = setInterval(this.next, 10000)
    },
    next: function () {
      this.currentStatement++
    },
    prev: function () {
      this.currentStatement--
    }
  }
}
</script>

<style scoped lang="scss">
.title-wrapper {
  position: relative;

  @include breakpoint($sm) {
    text-align: right;
  }

  h1.title {
    font-size: 28px;
    display: inline;
    line-height: 1.38;
    right: 0;
    position: absolute;
    bottom: 0;

    @include breakpoint($sm) {
      font-size: 55px;
    }

    div {
      display: inline;
    }
  }
}

.statement {
  margin-top: 40px;
}

.hero.is-primary {
  background-color: transparent;
  background-size: cover;
  height: calc(100vh - 75px);
  display: flex;

  .hero-body {
    display: flex;

    .container {
      flex: 1;
      align-self: flex-end;
    }
  }
}

.fade-enter-active, .fade-leave-active {
    transition: opacity .5s
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
    opacity: 0
}


</style>
