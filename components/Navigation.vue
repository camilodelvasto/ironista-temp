<template>
  <div class="nav-container">
    <nav class="navbar is-transparent"
      v-bind:class="{ 'expanded': showMobileMenu }"
    >
      <div class="container is-fluid navbar-container">
        <div class="navbar-brand">
          <Logo />
        </div>

        <div id="#nav-burger-trigger" class="navbar-burger"
          v-bind:class="{ 'is-active': showMobileMenu }"
          v-on:click="toggleMobileMenu()"
        >
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <div class="navbar-menu"
        v-bind:class="{ 'is-active': showMobileMenu }"
      >
        <div class="navbar-start"
          v-on:click="closeMobileMenu()"
        >
          <nuxt-link exact to="/" class="navbar-item">Inicio</nuxt-link>
          <nuxt-link to="/aprendizaje-colectivo" class="navbar-item">Aprendizaje Colectivo</nuxt-link>
          <a class="navbar-item" href="https://medium.com/ironista" target="_blank">Blog</a>
          <nuxt-link to="/contacto" class="navbar-item">Contacto</nuxt-link>
        </div>
        <div class="navbar-end"
          v-on:click="closeMobileMenu()"
        >
          <nuxt-link exact to="/" class="navbar-item">Acerca de</nuxt-link>
          <nuxt-link to="/como-lo-hacemos" class="navbar-item">¿Cómo?</nuxt-link>
          <nuxt-link to="/contacto" class="navbar-item">Contacto</nuxt-link>
        </div>
      </div>
    </nav>
  </div>
</template>

<style scoped lang="scss">
.navbar-burger {
  transform: translate(10px,13px);
  position: fixed;
  top: 0;
  right: 15px;

  @include breakpoint($bulma) {
    display: block;
    transform: translate(0px,13px);
  }

  span {
    width: 25px;
    margin-left: -12px;
    background-color: $color-bg-dark;

    &:nth-child(1) {
      margin-top: -10px;
    }

    &:nth-child(3) {
      margin-top: 8px;
    }
  }

  &.is-active {
    span {
      background-color: $color-bg-light;

      &:nth-child(1) {
        margin-top: -10px;
        margin-left: -7px;
      }

      &:nth-child(3) {
        margin-top: 8px;
        margin-left: -7px;
      }
    }
  }

  &:hover {
    background-color: inherit;

    span {
      background-color: $color-emphasis-alt;
    }
  }
}

@include breakpoint($xs) {
  .navbar-burger {
    &:hover {
      span {
        background-color: $color-bg-dark;
      }
    }
    &.is-active {
      &:hover {
        span {
          background-color: $color-bg-light;
        }
      }
    }
  }
}

.navbar-container {
  display: flex;
}

.nav-container {
  height: 75px;

  .navbar {
    position: fixed;
    left: 0;
    right: 0;
    z-index: 900;

    @include breakpoint($bulma) {
      display: flex;
      flex-direction: column;
    }

    &.expanded {
      background-color: $color-bg-dark;
      transition: background-color 0.2s ease-in-out;
      height: 100%;
      display: flex;
      flex-direction: column;
      bottom: 0;
    }
  }

  .navbar-menu {
    box-shadow: none;
    flex: 1;

    @include breakpoint($bulma) {
      padding: 0 40px;
    }

    a.navbar-item {
      font-family: $font-secondary;
      text-align: center;
      font-size: 30px;

      &:hover {
        text-decoration: underline;
      }

      @include breakpoint($sm) {
        font-size: 40px;
        text-align: right;
      }

      @include breakpoint($bulma) {
        display: block;
      }
    }

    &.is-active {
      display: flex;
      flex-direction: column;

      a.navbar-item {
        color: $color-text-light;

        &:hover {
          background-color: transparent;
          color: $color-emphasis-alt;
        }
      }

      @include breakpoint($bulma) {
        display: flex;
        flex-direction: column;
      }      
    }

    @include breakpoint($bulma) {
      display: none;
    }

    .navbar-start {
      padding-top: 60px;
      display: flex;
      flex-direction: column;

      @include breakpoint($bulma) {
        margin-right: 0;
        margin-left: auto;
      }
    }

    .navbar-end {
      flex-direction: row;
      flex: 1;
      align-items: flex-end;
      display: flex;
      justify-content: center;

      @include breakpoint($bulma) {
        align-items: center;
      }

      a.navbar-item {
        font-size: 16px;
        font-family: $font-primary;
        text-transform: lowercase;
        letter-spacing: 1px;

        @include breakpoint($bulma) {
          font-size: 20px;
        }
      }
    }
  }

  .navbar-brand {
    height: 75px;

    @include breakpoint($bulma) {
      transform: translateX(-20px);
    }
  }
}

</style>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data () {
    return {
      showMobileMenu: false,
      scrollTop: 0
    }
  },
  mounted () {
    this.showMobileMenu = false
    this.scrollTop = 0
  },
  methods: {
    toggleMobileMenu () {
      var vm = this
      vm.showMobileMenu = !vm.showMobileMenu
      if (vm.showMobileMenu) {
        vm.scrollTop = window.scrollY
        vm.openMobileMenu()
      } else {
        vm.closeMobileMenu()
        window.scrollTo(0, vm.scrollTop)
      }
    },
    closeMobileMenu () {
      var vm = this
      document.body.classList.remove('modal-open')
      vm.showMobileMenu = false
    },
    openMobileMenu () {
      var vm = this
      document.body.classList.add('modal-open')
      vm.showMobileMenu = true
    }
  }
}
</script>