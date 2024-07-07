<template>
  <div class="footer-section bg-primary" >
    <ContentLayout>
      <ContentSection>
        <div class="row">
          <div class="col-xs-12 col-md-3 q-pa-md">

          </div>

        </div>
        <div class="col-xs-12 col-md-12 q-pa-md">
        </div>
      </ContentSection>
      <div class="row text-center">
        <ul class="inline-list">
          <li v-for="lang in langs" :key="lang.locale" >
            <NuxtLink :to="switchLocalePath(lang.locale)">{{ lang.text }}</NuxtLink>
            <span class="seperator">|</span>
          </li>
        </ul>
      </div>
    </ContentLayout>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import ContentLayout from '../components/ContentLayout.vue';
import ContentSection from '../components/ContentSection.vue';

export default defineComponent({
  name: 'FooterSection',
  components: {
    ContentLayout,
    ContentSection,
  },
  setup() {
    const langs = ref([
      { locale: 'en', text: 'English (US)' },
      { locale: 'gb', text: 'English (UK)' },
      { locale: 'de', text: 'Deutsch' },
      { locale: 'es', text: 'Español' },
      { locale: 'fr', text: 'Français' },
      { locale: 'ru', text: 'Русский' },
      { locale: 'pl', text: 'Polski' },
      { locale: 'sk', text: 'Slovenský' },
      { locale: 'ja', text: '日本語' },
      { locale: 'ar', text: 'العربية' },
      { locale: 'nl', text: 'Nederlands' },
      { locale: 'ae', text: 'العربية (UAE)' },
      { locale: 'qa', text: 'العربية (Qatar)' },
      { locale: 'ir', text: 'فارسی (Iran)' },
      { locale: 'om', text: 'العربية (Oman)' },
      { locale: 'bh', text: 'العربية (Bahrain)' },
    ]);

    return {
      langs
    };
  },
});
</script>

<style lang="scss" scoped>
@import '../assets/scss/vars.scss';

.footer-section{
  min-height: $header-height*1;
}
.inline-list {
  list-style-type: none;
  padding: 0;
}

.inline-list li {
  display: inline-block;
  //margin-right: 10px;
}
a {
  color: lightgrey;
  text-decoration: none;
}

.seperator {
  margin: 0 5px;
  color: lightgrey;
}

/* Hide the separator for the last item in the loop */
ul.inline-list li:last-child .seperator {
  display: none;
}

</style>
