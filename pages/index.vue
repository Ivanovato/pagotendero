<template>
  <div id="home-page" class="page-wrapper home-page">
    <site-hero :title="title" :subtitle="subtitle" :image="featureImage">
      <button
        class="button is-primary"
        @click="$eventBus.$emit('modal-triggered', 'newsletter-modal')"
      >
        Conocer más
      </button>
    </site-hero>
    <!-- <main-section theme="sidebar-right">
      <template v-slot:default>
        <div class="content">
          <h2>
            Realizar pagos en linea a tu tienda de la esquina es posible.
          </h2>
          <p>
            <strong>
              Usando tecnologia segura de plataformas como EPAYCO-DAVIVIENDA.
            </strong>
          </p>
          <p>
            El Covid-19 o Coronavirus nos ha impactdo de forma social,
            economica, como:
          </p>
          <ul>
            <li>
              Evitar sitios donde se reunen de forma masiva las personas, de
              esta forma prevenimos el contagio.
            </li>
            <li>
              Interactuar más con la ayuda de tecnologia.
            </li>
            <li>
              Evitar sitios donde se reunen de forma masiva las personas, de
              esta forma prevenimos el contagio.
            </li>
            <li>
              Evitar sitios donde se reunen de forma masiva las personas, de
              esta forma prevenimos el contagio.
            </li>
          </ul>
          <p>
            Esta situación
          </p>

          <h3>Another Fake Heading</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci
            ratione rem repudiandae sit!
          </p>
          <quote-card />
          <h3>Still More Fake Content</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci
            ratione rem repudiandae sit! Lorem ipsum dolor sit amet, consectetur
            adipisicing elit.
            <strong>Alias aut facere harum ipsam</strong> quibusda veritatis.
          </p>
        </div>
      </template>
      <template v-slot:sidebar>
        <div class="index-1">
          <strong>
            Ayuda a tu negocio de barrio ya sea una tienda, papeleria,
            dorgueria, fama
          </strong>
        </div>
      </template>
    </main-section> -->
    <main-section theme="one-column">
      <template v-slot:default>
        <!-- All Posts -->
        <posts-grid />
      </template>
      <template v-slot:sidebar>
        No hay nada aquí
      </template>
    </main-section>
    <news-letter-form-modal />
  </div>
</template>

<script>
import { mapState } from 'vuex'
import { setPageData } from '../helper'
import NewsLetterFormModal from '~/components/NewsLetterFormModal'
export default {
  name: 'HomePage',
  components: {
    NewsLetterFormModal
  },
  head() {
    return {
      title: `Inicio | ${this.$siteConfig.siteName}`
    }
  },
  computed: {
    ...mapState(['title', 'subtitle', 'featureImage'])
  },
  fetch({ store, params }) {
    setPageData(store, { slug: 'home' })
  }
}
</script>

<style>
.home-page .under-subtitle {
  border-top: none;
}
.index-1 {
  text-align: justify;
}
</style>
