<template>
	<!-- <div>
    <NuxtWelcome />
  </div> -->
	<div :class="textAlignmentClass">
		<HeaderSection />
		<NuxtPage />
    <FooterSection></FooterSection>
	</div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';
import HeaderSection from '../components/HeaderSection.vue';
import FooterSection from "~/components/FooterSection.vue";
import {computed, ref} from "vue";
const windowWidth = ref(0);
const { t } = useI18n();
const imageSrc = computed(() => {
  return windowWidth.value < 1024
      ? 'https://abriumbi.sirv.com/volker-vogelringzange/bg-mobile.webp'
      : 'https://abriumbi.sirv.com/volker-vogelringzange/bg-desktop.webp';
});
const { locale } = useI18n();

const textAlignmentClass = computed(() => {
  return ['ar','ae','qa','ir','om','bh'].includes(locale.value) ? 'text-right' : 'text-left';
});

useSeoMeta({
  title: t('seo.title'),
  ogTitle: t('seo.description'),
  description: t('seo.title'),
  ogDescription: t('seo.description'),
  ogImage: imageSrc,
  twitterCard: 'https://abriumbi.sirv.com/volker-vogelringzange/bg-desktop.webp',
  // robots: 'index',
})
</script>
