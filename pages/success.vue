<template>
  <div class="index">
    <section id="contacto">
      <div class="container">
        <div class="form-intro">
          <h1>Hemos recibido su mensaje</h1>
          <p>Gracias, {{ senderName }}, por su mensaje. En breve nos pondremos en contacto.</p>
        </div>
        <div>
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
  },
  computed: {
    senderName () {
      return this.$route.query.name
    }
  }
}
</script>

<style scoped lang="scss">
.form-intro {
  text-align: center;
  margin-top: 40px;
  margin-bottom: 40px;
}

form {
  @include breakpoint($sm) {
    width: 60%;
    margin: 0 auto;
  }
}

</style>
