<template>
  <div class="picture">
    <div class="picture-container" :style="{backgroundImage: 'url(' + image + ')'}"></div>
  </div>
</template>

<script>
export default {
	name: 'Photo',
	props: {
		image: String
	}
}
</script>

<style scoped lang="sass">
	.picture
		display: flex
		align-items: center
		justify-content: center
		width: 100%
		height: 100%

	.picture-container
		width: 100%
		height: 100%
		background-size: contain
		background-repeat: no-repeat
		background-position: center
		overflow: hidden
		animation-name: sad
		animation-duration: 30s
		animation-fill-mode: forwards
		animation-timing-function: linear
		animation-iteration-count: infinite

	@keyframes sad
		0%
			opacity: 0
			transform: scale(1)
			filter: grayscale(0)
		5%
			opacity: 1
		20%
			filter: grayscale(100%)
		95%
			opacity: 1
		100%
			opacity: 0
			transform: scale(1.2)
			filter: grayscale(100%)
</style>