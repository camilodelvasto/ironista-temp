<template>
  <div class="index">
    <section class="statement">
      <div class="container">
        <div class="font-text">
          <h1>Hemos recibido su mensaje</h1>
          <p>Gracias, {{ senderName }}, por su mensaje. En breve nos pondremos en contacto.</p>
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
</style>
