<template>
  <div class="index">
    <section class="hero is-primary is-medium"
      v-bind:style="{ backgroundImage: `url('${heroImage}')` }"
    >
      <div class="hero-body">
        <div class="container">
          <div class="title-wrapper" v-for="(statement, index) in statements" >
            <transition name="fade">
              <h1 class="title" v-if="index === currentStatement % statements.length">
                <div v-html="statement"></div>
              </h1>
            </transition>
            <a v-smooth-scroll="{ duration: 500, offset: -74 }" href="#aprendizaje-intro" class="hero-chevron">
              <ChevronDown class="bounce-always" />
            </a>
          </div>
        </div>
      </div>
    </section>

    <section class="statement" id="aprendizaje-intro">
      <div class="container">
        <div class="font-text">
          <div class="statement-body">Nuestro punto de partida es la esperanza y la convicción de que podemos ser mejores juntos a través del </div>
          <nuxt-link to="/aprendizaje-colectivo" class="statement-emphasis">aprendizaje colectivo.</nuxt-link>
        </div>
      </div>
    </section>

    <section class="areas" id="areas">
      <div class="container columns is-multiline">
        <div class="card column is-4" v-for="area in areas">
          <nuxt-link :to="area.link">
            <div class="card-image">
              <figure class="image is-4by3">
                <img :src="area.img" alt="Image">
              </figure>
            </div>
          </nuxt-link>
          <div class="card-content">
            <h4>{{ area.title }}</h4>
            <nuxt-link :to="area.link">
              <div class="content">
                {{ area.intro }}
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </section>

    <BlackFooter />
  </div><!--container-->
</template>

<script>
import ChevronDown from '~/components/ChevronDown.vue'
import BlackFooter from '~/components/BlackFooter.vue'

export default {
  transition: 'page',
  components: {
    ChevronDown,
    BlackFooter
  },
  data () {
    return {
      statements: [
        '<span class="title-standard">Para un ironista, el camino para cambiarnos como sociedad es la </span><span class="title-emphasis">redescripción.</span>',
        '<span class="title-standard">No se trata de descubrir la fórmula para cambiar el mundo, sino de </span><span class="title-emphasis">imaginar una nueva forma de describirnos </span><span class="title-standard">como sociedad.</span>'
      ],
      areas: [
        { title: 'Violencia', intro: 'En la crianza, en la pareja, en la escuela, en la calle', link: 'violencia', img: 'https://res.cloudinary.com/startics/image/upload/v1507670982/violencia_ysx2gv.jpg' },
        { title: 'Gestión del riesgo', intro: 'Seguridad vial, seguridad en internet, decisiones financieras', link: 'riesgo', img: 'https://res.cloudinary.com/startics/image/upload/v1507670983/riesgo_w5ptw4.jpg' },
        { title: 'Irracionalidad', intro: 'Consumo irracional, sostenibilidad', link: 'irracionalidad', img: 'https://res.cloudinary.com/startics/image/upload/v1507670988/irracionalidad_ksapmi.jpg' }
      ],
      currentStatement: 0,
      timer: null,
      heroImage: require('~/assets/img/street-art-graffiti.jpg')
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

.hero-chevron {
  position: absolute;
  margin: 0 auto;
  left: 0;
  right: 0;
  width: 100px;
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
      margin-bottom: 50px;
    }
  }
}

.fade-enter-active, .fade-leave-active {
    transition: opacity .5s
}
.fade-enter, .fade-leave-to {
    opacity: 0
}

.chevron-down {
  fill: rgba(white, 0.4);
  width: 100px;
  height: 100px;
}

.columns {
  margin: 20px auto;

  @include breakpoint($sm) {
    margin: 40px auto;
  }

}

.card {
  box-shadow: none;

  .card-content {
    padding: 1em 0;
    font-size: 28px;

    @include breakpoint($sm) {
      font-size: 34px;
    }
  }

  a {
    .content {
      color: $color-text;
    }

    &:hover {
      text-decoration: underline;
      color: $color-emphasis;
    }
  }

  .card-image {
    overflow: hidden;
    border-bottom: 8px solid $color-emphasis-alt;
  }

  figure {
    transform: scale(1);
    transition: transform 0.2s ease-in-out;

    &:hover {
      transform: scale(1.02);
    }

    img {
      object-fit: cover;
    }
  }
}
</style>
