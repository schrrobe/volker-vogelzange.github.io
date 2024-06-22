<template>
	<!-- <div>
    <NuxtWelcome />
  </div> -->
	<div :class="textAlignmentClass">
		<HeaderSection />
		<NuxtPage />
	</div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';
import HeaderSection from '../components/HeaderSection.vue';

const { locale } = useI18n();

const textAlignmentClass = computed(() => {
	return locale.value === 'ar' ? 'text-right' : 'text-left';
});
</script>
