<template>
	<div class="section fp-noscroll">
		<div class="animate-me">
			漫漫星程，你我同行~
		</div>
		<div class="animate-me">
			Driven by dreams, not by profit.
		</div>
		<div class="animate-me">
			星梦启航，代码笔记。
		</div>
		<div class="animate-me">
			让学习少走弯路，让工作得心应手!
		</div>
		<div class="animate-me">
			信息互联，资源无限。
		</div>
		<div class="animate-me">
			一站式导航，学习新体验。
		</div>
		<div class="animate-me">
			整合推荐，减少信息差。
		</div>
		<div class="animate-me">
			发现世界，连接资源。
		</div>
		<div class="animate-me">
			资源一站通，信息无阻挡。

		</div>

	</div>
</template>

<script setup>
import anime from 'animejs/lib/anime.es.js';
import Letterize from 'letterizejs';
import { onMounted } from 'vue';

const initAnime = () => {

	const test = new Letterize({
		targets: ".animate-me"
	});

	const maxGridSize = 10; // 设置一个合理的最大值
	const animation = anime.timeline({
		targets: test.listAll,
		delay: anime.stagger(100, {
			grid: [maxGridSize, test.list.length], // 使用固定的 grid 大小
			from: "center"
		}),
		loop: true
	});

	animation
		.add({
			scale: 0.5
		})
		.add({
			letterSpacing: "10px"
		})
		.add({
			scale: 1
		})
		.add({
			letterSpacing: "6px"
		});

};

onMounted(() => {
	initAnime();
});
</script>

<style scoped>
.section {
	display: flex;
	align-items: center;
	justify-content: center;
}

div.animate-me {
	font-weight: 400;
	font-size: 2vw;
	display: flex;
	align-items: center;
	justify-content: center;
	text-align: center;
	box-sizing: border-box;
	letter-spacing: 6px;
	margin: 0;
	line-height: 1.2;
}

span {
	display: inline-block;
}
</style>