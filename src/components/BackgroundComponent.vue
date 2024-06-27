<template>
	<div class="background-container">
		<div v-if="backgroundType === 'color'" :style="{ backgroundColor: backgroundSource }" class="background"></div>
		<img v-if="backgroundType === 'image'" :src="backgroundSource" alt="background image" class="background" />
		<iframe v-if="backgroundType === 'webpage'" :src="backgroundSource" class="background"></iframe>
		<video v-if="backgroundType === 'video'" :src="backgroundSource" autoplay loop muted class="background"></video>
	</div>
</template>

<script>
export default {
	name: 'BackgroundComponent',
	props: {
		backgroundType: {
			type: String,
			required: true,
			validator: value => ['color', 'image', 'webpage', 'video'].includes(value)
		},
		backgroundSource: {
			type: String,
			required: true
		}
	}
}
</script>

<style scoped>
.background-container {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	overflow: hidden;
	z-index: -1;
	/* Ensure the background is behind other content */
}
iframe{
	border: 0;
	margin: 0;
	padding: 0;
}
.background {
	width: 100%;
	height: 100%;
	object-fit: cover;
	/* Ensures the media covers the whole container */
}
</style>