<template>
  <section>
    <div class="row justify-center">
      <div class="col-md-3 col-xs-12" v-for="img in images" :key="img.src">
        <lazy-nuxt-img :src="img.src" width="100%" :height="img.height? img.height : '400'"></lazy-nuxt-img>
      </div>

    </div>
  </section>
</template>

<script setup lang="ts">
import { useI18n } from 'vue-i18n';

const { t } = useI18n();

const images = [
  {
    src: '1.jpg',
    altText: 'Beringungszange für Adressringe auf einem Stein mat anderen Falknersachen',
  },
  {
    src: 'g9.jpeg',
    altText: 'Weimaranerhund und Gerfalke auf einer Wiese',
  },
  {
    src: 'g3.jpg',
    altText: 'Rackelwild wird beringt',
  },
  {
    src: 'g4.jpg',
    altText: 'Adressringzange für Ente ',
  },
  {
    src: '2.jpg',
    altText: 'Greifvogel Adressringzange',
  },
  {
    src: 'g6.jpg',
    altText: 'Adressringzange mit anderen Falknersachen',
  },
  {
    src: 'g7.jpg',
    altText: 'Ente wird beringt',
  },
  {
    src: 'g8.jpeg',
    altText: 'Gerfalke jagd KrähenS',
  },
]

</script>

<style scoped lang="scss">
@import '../assets/scss/styles.scss';

</style>