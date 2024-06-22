<template>
	<q-carousel
		v-model="slide"
		class="carousel"
		style="height: 70vh;"
		animated
		arrows
		navigation
		infinite
	>
		<q-carousel-slide
			:name="1"
      :img-src="imageSrc"
		>
			<content-layout full-height>
				<content-section full-height>
					<div class="show-mobile">
						<div class="row justify-center content-center">
							<div class="glass-box">
								<h1 class="glass-box-title">
									<strong>{{ $t('homeView.titleHighligted') }}</strong> {{ $t('homeView.title') }}
								</h1>
							</div>
						</div>
					</div>
					<div class="show-desktop">
						<div class="row justify-end content-end">
							<div class="glass-box">
								<h1 class="glass-box-title">
									<strong>{{ $t('homeView.titleHighligted') }}</strong> {{ $t('homeView.title') }}
								</h1>
							</div>
						</div>
					</div>
				</content-section>
			</content-layout>
		</q-carousel-slide>
	</q-carousel>
</template>

<script>
import { defineComponent, ref, reactive, computed, onMounted, onUnmounted } from 'vue';
import ContentLayout from '../components/ContentLayout.vue';
import ContentSection from '../components/ContentSection.vue';

export default defineComponent({
  name: 'HomeSlider',
  setup() {
    const windowWidth = ref(0);

    const imageSrc = computed(() => {
      return windowWidth.value < 1024 
        ? 'https://abriumbi.sirv.com/volker-vogelringzange/bg-mobile.webp'
        : 'https://abriumbi.sirv.com/volker-vogelringzange/bg-desktop.webp';
    });

    const updateWindowWidth = () => {
      windowWidth.value = window.innerWidth;
    };

    onMounted(() => {
      updateWindowWidth(); // Initial setting of window width
      window.addEventListener('resize', updateWindowWidth);
    });

    onUnmounted(() => {
      window.removeEventListener('resize', updateWindowWidth);
    });

    return {
      slide: ref(1),
      imageSrc
    };
  },
});
</script>


<style lang="scss">
@import '../assets/scss/main.scss';

.carousel{
    height: 70vh;
}

.glass-box {
  width: fit-content;
  padding: $pad $pad*2;
  margin-top: 5vh;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(7.1px);
  -webkit-backdrop-filter: blur(7.1px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  @include bp(m){
    margin-top: 20vh;
  }
}

.triangle {
  width: 100%;
  height: 70vh;
  border-right: 60vw solid transparent;
  border-bottom: 120vw solid rgba(255, 255, 255, 0.7);
  background-image: url('https://cdn.quasar.dev/img/mountains.jpg');
  background-repeat: no-repeat;
  // backdrop-filter: blur(7.1px);
}

.glass-bg{
  background-color: rgba(255, 255, 255, 0.7) ;
  border-radius: 16px;
  backdrop-filter: blur(7.1px);
  padding: $pad;
  margin-top: 10%

}
</style>
