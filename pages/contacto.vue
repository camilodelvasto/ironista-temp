<template>
  <div class="index">
    <section id="contacto">
      <div class="container">
        <div class="form-intro">
          <h1>Entremos a hablar</h1>
          <p>Ironista trabaja con gobiernos locales y organizaciones de todos los tamaños, realizando proyectos de cambio cultural, organizacional y aprendizaje colectivo.</p>
        </div>
        <div>
          <TestForm />
          <form netlify action="/success" name="contact-form">
            <div class="field">
              <label class="label"><h4>Nombre</h4></label>
              <div class="control">
                <input class="input" type="text" placeholder="Nombre completo" name="name" required>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Email</h4></label>
              <div class="control">
                <input class="input" type="email" placeholder="Email" name="email" required="">
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Asunto</h4></label>
              <div class="control">
                <div class="select">
                  <select>
                    <option>Quiero realizar un proyecto con Ironista</option>
                    <option>Quiero escribir para Ironista</option>
                    <option>Quiero trabajar para Ironista</option>
                    <option>Otro</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Mensaje</h4></label>
              <div class="control">
                <textarea class="textarea" placeholder="Su mensaje" name="message" required=""></textarea>
              </div>
            </div>
            <button class="button button-cta" type="submit">Enviar</button>
          </form>
        </div>
      </div>
    </section>

    <BlackFooter />
  </div><!--container-->
</template>

<script>
import BlackFooter from '~/components/BlackFooter.vue'
import TestForm from '~/components/TestForm.vue'

export default {
  transition: 'page',
  components: {
    BlackFooter,
    TestForm
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
