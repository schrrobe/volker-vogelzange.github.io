<template>
	<!-- <div class="q-pa-md"></div> -->
	<div>
		<home-slider />
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
	</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import HomeSlider from '../components/HomeSlider.vue';
import HomeWelcome from '../components/HomeWelcome.vue';
import ContentLayout from '../components/ContentLayout.vue';
import ContentSection from '../components/ContentSection.vue';
import RingSizeSection from '../components/RingSizeSection.vue';

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
</script>

<style>
</style>
