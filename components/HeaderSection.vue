<template>
	<div class="header-section bg-primary" />
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
	name: 'HeaderSection',
});
</script>

    <style lang="scss">
    @import '../assets/scss/vars.scss';

    .header-section{
        height: $header-height;
    }
</style>
