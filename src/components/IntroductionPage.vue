<template>
	<div id="fullpage">
		<div class="section">
			<h1>Welcome to 星梦启航</h1>
			<p>我们的目标是减少信息差，整合推荐资源。</p>
		</div>
		<div class="section">
			<h1>我们的服务</h1>
			<p>提供各种资源导航，帮助你快速找到需要的信息。</p>
		</div>
		<div class="section">
			<h1>联系我们</h1>
			<p>如果你有任何问题，请随时联系我们。</p>
		</div>
	</div>
</template>

<script>
import fullpage from 'fullpage.js';

export default {
	name: 'IntroductionPage',
	mounted() {
		new fullpage('#fullpage', {
			// Fullpage.js 配置
			autoScrolling: true,
			navigation: true,
		});
	},
};
</script>

<style scoped>
.section {
	text-align: center;
	font-size: 2em;
	padding: 20px;
}
</style>