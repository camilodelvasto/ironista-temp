<template>
  <div class="index">
    <section id="contacto">
      <div class="container">
        <div class="form-intro">
          <h1>Entremos a hablar</h1>
          <p>Ironista trabaja con gobiernos locales y organizaciones de todos los tamaños, realizando proyectos de cambio cultural, organizacional y aprendizaje colectivo.</p>
        </div>
        <div>
          <form action="https://d12naj40.insight.ly/WebToLead/Create" name="insightly_web_to_lead" method="post">
            <input type="hidden" name="formId" value="CyZLBiAjCACnEw2h0QAvHw==" />
            <input type="hidden" name="ResponsibleUser" value="1422507"/>
            <input type="hidden" name="LeadSource" value="1967093"/>
            <div class="field">
              <label class="label"><h4>Nombre</h4></label>
              <div class="control">
                <input class="input" type="text" placeholder="Nombre" name="FirstName" required>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Apellido</h4></label>
              <div class="control">
                <input class="input" type="text" placeholder="Apellido" name="LastName" required>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Email</h4></label>
              <div class="control">
                <input class="input" type="email" placeholder="Email" name="email" required="">
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Teléfono</h4></label>
              <div class="control">
                <input class="input" type="text" placeholder="Teléfono" name="phone" required>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Organización</h4></label>
              <div class="control">
                <input class="input" type="text" placeholder="Organización" name="OrganizationName" required>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Asunto</h4></label>
              <div class="control">
                <div class="select">
                  <select name="Industry">
                    <option value="hire-us">Quiero realizar un proyecto con Ironista</option>
                    <option value="write-for-us">Quiero escribir para Ironista</option>
                    <option value="work-for-us">Quiero trabajar para Ironista</option>
                    <option value="other">Otro</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="field">
              <label class="label"><h4>Mensaje</h4></label>
              <div class="control">
                <textarea class="textarea" placeholder="Su mensaje" name="Description" required=""></textarea>
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

export default {
  transition: 'page',
  components: {
    BlackFooter
  },
  data () {
    return {
      empty: ' '
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
