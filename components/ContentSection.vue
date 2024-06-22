<template>
	<div class="section">
		<slot />
	</div>
</template>

<script setup>
// import { defineProps } from 'vue';

// const props = defineProps({
// 	fullHeight: {
// 		type: Boolean,
// 		default: false,
// 	},
// 	mt: {
// 		type: String,
// 		required: false,
// 		default: '40px',
// 	},
// 	mb: {
// 		type: String,
// 		required: false,
// 		default: '60px',
// 	},
// });

// const classes = computed(() => {
//   return {
//     'full-height': props.fullHeight,
//   };
// });
</script>

<style lang="scss">
@import '../assets/scss/styles.scss';

.section {
  padding: $pad $pad;
  margin-top: 30px;
  margin-bottom: 60px;

  @include bp(m){
    padding: $pad $pad * 2;
  }

  .full-height {
    height: 100%;
  }
}
</style>
