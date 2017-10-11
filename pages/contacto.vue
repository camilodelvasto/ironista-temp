<template>
  <div class="index">
    <section class="statement" id="contacto">
      <div class="container">
        <div class="font-text">
          <div class="statement-body">
            Forma de contacto            
          </div>
        </div>
      </div>
    </section>

    <Footer />
  </div><!--container-->
</template>

<script>
import Footer from '~/components/Footer.vue'

export default {
  transition: 'page',
  components: {
    Footer
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
