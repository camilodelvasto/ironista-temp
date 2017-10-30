<template>
  <div class="index">
    <section id="aprendizaje-colectivo">
      <div class="container page-content">
        <div class="font-text">
          <h1>Aprendizaje colectivo</h1>
        </div>

        <blockquote>
          Todos los estudiantes dijeron que no querían beber más de 6 cervezas en una noche. 
          Pero todos creían que los demás beberían más de 10.
          Al final, todos terminaron bebiendo más de 10 cervezas. 
        </blockquote>

        <figure>
          <img v-bind:src="pageImg" alt="Chicos bebiendo">
          <figcaption>Comportamiento de grupo: los individuos no se comportan igual cuando están solos.</figcaption>
        </figure>

        <p>Con frecuencia creemos que para cambiar la sociedad debemos educar a sus individuos. Y pasa el tiempo y seguimos igual.</p>
        <p>La sociedad es más que la suma de individuos. Nuestro comportamiento social no se rige tan sólo por criterios individuales sino por nuestras representaciones y expectativas sobre el comportamiento de los demás.</p>
        <p>Transformar un grupo social requiere mucho más que concientización de los individuos. Requiere trabajar en la transformación de las normas tácitas que regulan al grupo, en la transformación de las creencias sobre lo deseable y las expectativas mutuas sobre el comportamiento del otro.</p>
        <h4>¿Cuál es, entonces, la pregunta?</h4>
        <p>Nada de eso se puede aprender individualmente porque es justo en la interacción entre unos y otros que esas normas se refuerzan o se violan, fortaleciendo las expectativas de cumplimiento de normas pro sociales o la desesperanza compartida.</p>

        <p>Los colombianos tenemos grandes retos para avanzar como sociedad: lograr trabajar cooperativamente, cultivar la empatía, gestionar el riesgo socialmente, interiorizar formas de comunicación alternativas a la violencia, coordinarnos para producir bienes públicos, entre otros.</p>
        <p>Todos estos retos requieren de un gran número de transformaciones simultáneas en nuestras prácticas, pero también en nuestras creencias compartidas, narrativas, conocimientos, explicaciones, deseos y expectativas.</p>
        <p>El único camino para lograr estas transformaciones es el aprendizaje colectivo, que es un lugar de experimentación interdisciplinaria, que conjuga los conocimientos más relevantes de las ciencias sociales en los últimos treinta años con las infinitas y aún inimaginadas posibilidades creativas que brinda el arte, la comunicación, la pedagogía y la innovación.</p>


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
      pageImg: require('~/assets/img/bebiendo.jpg')
    }
  }
}
</script>

<style scoped lang="scss">

</style>
