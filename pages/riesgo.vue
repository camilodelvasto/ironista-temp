<template>
  <div class="index">
    <section id="aprendizaje-colectivo">
      <div class="container page-content">
        <div class="font-text">
          <h1>Riesgo</h1>
        </div>

        <figure>
          <img v-bind:src="pageImg" alt="Peatones en Bucaramanga">
          <figcaption>El riesgo va más allá de la integridad humana.</figcaption>
        </figure>

        <p>Los riesgos emanan cada vez menos del mundo natural y más de la elección y acción humana. La vida moderna presenta un mayor número de riesgos ocasionados puramente por sociedad  y sus avances como la manipulación genética, la persistencia de armas nucleares, la propagación del VIH, los accidentes químicos o las explosiones nucleares, o incluso los accidentes aéreos y automovilísticos.</p>
        <p>Sin embargo, estos riesgos no son percibidos de igual manera en todo el globo terráqueo. Los individuos, grupos e instituciones suelen percibir algunos riesgos pero no otros. Algunos riesgos generan preocupación o alarma mientras que otros son deliberada o inconscientemente ignorados. Algunos atraen atención de los gobernantes y prácticas de gestión del riesgo, mientras que otros no. La teoría cultural sugiere que la identificación de los riesgos es un proceso social y que los riesgos no existen en la realidad objetiva sino en la conciencia colectiva de las culturas. El riesgo es entonces una representación de los sistemas de creencias colectivos. Por lo tanto, cabe afirmar que el riesgo es un fenómeno cultural y no un fenómeno físico (Rosa 1998, p. 21).</p>
        <blockquote>Por esta razón, los distintos grupos humanos, países y culturas, tienen formas muy distintas de enfrentar el riesgo. En las sociedades modernas occidentales el manejo del riesgo se ha convertido en una de las principales actividades y en un indicador del éxito de la sociedad. Para ello han elaborado complejos sistemas de cálculo del riesgo e instituciones para reducirlo.</blockquote>
        <p>La función del manejo del riesgo es anticipar los resultados de situaciones de riesgo e incorporar la incertidumbre dentro de la toma de decisiones. El manejo del riesgo implica evitar resultados indeseados en ocasiones, y que el impacto de lo inevitable sea mitigado, siempre que las conexiones entre causa y efecto se establezcan correctamente (Jaeger et al. 2001, p.18). En el primer caso, el manejo del riesgo orientado a evitar lo indeseable podría llamarse prevención y comprende normas, técnicas y artefactos, con frecuencia asociados a prácticas de seguridad. Por el contrario, el manejo de riesgo orientado a mitigar el impacto de lo inevitable podría denominarse transferencia del riesgo, dentro de la cual se encuentra el seguro como principal instrumento para la transferencia de riesgo. Más adelante profundizaremos en cada uno de estas formas de manejo del riesgo.</p>

        <div class="desktop-reduced">
          <ShareTools />
        </div>
      </div>
    </section>

    <BlackFooter />
  </div><!--container-->
</template>

<script>
import BlackFooter from '~/components/BlackFooter.vue'
import ShareTools from '~/components/ShareTools.vue'

export default {
  transition: 'page',
  components: {
    BlackFooter,
    ShareTools
  },
  data () {
    return {
      pageImg: require('~/assets/img/peatones.jpg')
    }
  }
}
</script>

<style scoped lang="scss">

</style>
