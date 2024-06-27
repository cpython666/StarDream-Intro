<template>
	<div class="section">

		<div id="logo">
			<img id="ship" src="/imgs/ship.svg" />
			<img id="sun" src="/imgs/sun.svg" />
			<img id="moon" src="/imgs/moon.svg" />
			<svg id="pathsvg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 302 202">
				<path id="sunPath" d="M1,101 a150,100 0 1,1 0,1 Z" style="fill: none; stroke: none;" />
				<ellipse id="moonPath" cx="150" cy="100" rx="150" ry="100" style="fill: none; stroke: none;" />
			</svg>
		</div>
		<div id="box-cursor">
			<span id="box"></span>

		</div>
	</div>
</template>

<script setup>
import anime from 'animejs/lib/anime.es.js';
import Typed from 'typed.js';

import { onMounted } from 'vue';
const initAnime = () => {
	const sunPath = anime.path('#sunPath');
	const moonPath = anime.path('ellipse');

	anime({
		targets: '#sun',
		translateX: sunPath('x'),
		translateY: sunPath('y'),
		duration: 6000,
		loop: true,
		easing: 'linear'
	});

	anime({
		targets: '#moon',
		translateX: moonPath('x'),
		translateY: moonPath('y'),
		duration: 6000,
		loop: true,
		easing: 'linear'
	});
}
const initCursor = () => {
	const options = {
		strings: [
			"Driven by `dreams`^500, not by profit.^2500",
			'漫漫星程，你我同行~^1000',
			'星梦启航，代码笔记。^1000',
			'让学习少走弯路，让工作得心应手!^1000',
			'我于这喧嚣世界寻得`一方净土`，可我却已成净土所厌的喧嚣。^3000',
			'信息互联，资源无限。^1000',
			"一站式导航，学习新体验。^1000",
			"整合推荐，减少信息差。^1000",
			"发现世界，连接资源。^1000",
			"资源一站通，信息无阻挡。^1000",
			"资源连接，个性化待办。^1000",
		],
		typeSpeed: 150,
		showCursor: true,
		cursorChar: '_🌟',
		loop: true,
		loopCount: 200
	};
	new Typed('#box', options);
}
onMounted(
	() => {
		initCursor()
		initAnime()
	});

</script>

<style scoped>
.section {
	display: flex;
	align-items: center;
	justify-content: center;
}

#logo {
	width: 600px;
	height: 600px;
	display: flex;
	align-items: center;
	justify-content: center;
	position: absolute;
	top: 35%;
	left: 50%;
	transform: translate(-50%, -50%);
}

#logo img {
	position: absolute;
}

svg {
	width: 200px;
	position: absolute;
}

#sun,
#moon {
	width: 50px;
	height: 50px;
	left: 175px;
	top: 210px;
	position: absolute;
	color: rgb(222, 225, 228);
}

#ship {
	width: 200px;
}


#box-cursor {
	top: -300px;
	display: flex;
	flex-direction: row;
	justify-content: center;
	align-items: center;
	font-size: 36px;

}

#box {
	position: relative;
	width: auto;
	height: auto;
	border-radius: 20px;
	background: linear-gradient(to right bottom, rgba(162, 158, 158, 0.6), rgba(236, 228, 228, 0.1));
	backdrop-filter: blur(2px);
	box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.2);
	border-top: 1px solid rgba(255, 255, 255, 0.8);
	border-left: 1px solid rgba(255, 255, 255, 0.8);

	height: 55px;
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 6px 10px;
}
</style>