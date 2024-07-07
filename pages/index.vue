<template>
	<!-- <div class="q-pa-md"></div> -->
	<div>
		<home-slider />
    <content-layout>
      <content-section>
        <price-section></price-section>
      </content-section>
    </content-layout>
		<content-layout>
			<content-section>
				<home-welcome />
			</content-section>
		</content-layout>
		<content-layout class="bg-primary">
			<content-section>
				<ring-size-section />
			</content-section>
		</content-layout>
    <content-layout>
      <content-section>
        <more-benefits>
        </more-benefits>
      </content-section>
    </content-layout>
        <gallery></gallery>
	</div>
</template>

<script lang="ts">
import HomeSlider from '../components/HomeSlider.vue';
import HomeWelcome from '../components/HomeWelcome.vue';
import ContentLayout from '../components/ContentLayout.vue';
import ContentSection from '../components/ContentSection.vue';
import RingSizeSection from '../components/RingSizeSection.vue';
import MoreBenefits from "../components/MoreBenefits.vue";
import gallery from "../components/gallery.vue"

import { defineComponent, ref } from 'vue';

const slide = ref(1);
export default defineComponent({
	name: 'HomeView',
	setup() {
		return {
			slide: ref(1),
		};
		// Setup-Logik hier
	},
});

// useSeoMeta({
//   title: 'Beringungszange für Adressringe',
//   ogTitle: 'Beringungszange für Adressringe',
//   description: 'This is my amazing site, let me tell you all about it.',
//   ogDescription: 'This is my amazing site, let me tell you all about it.',
//   ogImage: 'https://example.com/image.png',
//   twitterCard: 'summary_large_image',
//   // robots: 'index',
// })
</script>

<style>
</style>
