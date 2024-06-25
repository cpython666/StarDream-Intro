<template>
	<div id="fullpage">
		<WelcomePage />
		<ServicesPage />
		<ContactPage />
	</div>
</template>

<script setup>
import { onMounted } from 'vue';
import fullpage from 'fullpage.js';
import 'fullpage.js/dist/fullpage.css';

import WelcomePage from './WelcomePage.vue';
import ServicesPage from './ServicesPage.vue';
import ContactPage from './ContactPage.vue';

onMounted(() => {
	new fullpage('#fullpage', {
		autoScrolling: true,
		navigation: true,
	});
});
</script>

<style scoped>
/* 可以根据需要添加全局样式 */
</style>