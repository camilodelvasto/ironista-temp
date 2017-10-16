<template>
  <section class="footer hero is-medium hero-final-statement">
    <div class="hero-body">
      <div class="container">
        <h1>¿Está listo para iniciar el cambio?</h1>
        <p><nuxt-link to="/contacto">Contáctenos</nuxt-link> para crear juntos una nueva forma de describirnos como sociedad.</p><br>
        <h4>Colombia</h4>
        <p>
          Calle 93 # 19-55, Piso 9<br>
          110221, Bogotá<br>
          <a href="mailto:hola@ironista.com">hola@ironista.com</a><br>
        </p>
        <h1 class="h1-answer"><nuxt-link to="/contacto">¡Hablemos!</nuxt-link></h1>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.footer {
  padding: 20px 0;
  background-color: $color-bg-dark;
  position: relative;

  .hero-body {
    padding: 0;
  }

  h1 {
    color: white;
    margin-bottom: 15px;
  }

  p {
    color: $color-bg-1;
  }

  a {
    color: $color-emphasis-alt;
  }

  h1.h1-answer {
    text-align: right;

    a {
      color: $color-emphasis-alt;

      &:hover {
        text-decoration: underline;
      }
    }
  }
}

</style>

<script>
</script>