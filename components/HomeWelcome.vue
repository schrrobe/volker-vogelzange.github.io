<template>
	<div class="container-flex">
		<div class="q-mt-xl">
			<h2>
				{{ $t('homeView.iconBoxTitle') }}
			</h2>
			<hr>
		</div>
		<div
			class="row"
			style="margin-top: 100px;"
		>
			<div
				v-for="iconBox in iconBoxes"
				:key="iconBox.icon"
				class="col-xs-12 col-md-3"
			>
				<div class="column items-center q-mb-lg">
					<q-icon
						:name="iconBox.icon"
						size="64px"
						color="primary"
						class="q-mb-lg"
					/>
					<h3>{{ iconBox.text }}</h3>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
import { useI18n } from 'vue-i18n';

const { t } = useI18n();

const iconBoxes = [
	{
		icon: 'plumbing',
		text: t('homeView.iconBox.ringSize'),
	},
	{
		icon: 'close',
		text: t('homeView.iconBox.ringDestruction'),
	},
	{
		icon: 'thumb_up',
		text: t('homeView.iconBox.easyHandling'),
	},
	{
		icon: 'handyman',
		text: t('homeView.iconBox.quality'),
	},
];
</script>
