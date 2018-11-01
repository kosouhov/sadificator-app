<template>
	<div class="upload">
		<div class="wrapper">
			<div class="upload__header">
				<div class="header">
					<div class="header__title">Sadificator</div>
					<div class="header__subtitle">Make your look sad</div>
				</div>
			</div>
			<div class="upload__content">
				<div class="content">
					<div class="content__input">
						<input type="file" name="file" id="file" class="content__input-hidden" @change="change">
						<label for="file" class="content__input-label">{{ message }}</label>
						<button v-if="button" class="content__input-button" @click="$emit('buttonClick')">Sadificate me</button>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Upload',
	props: {
		message: String,
		button: Boolean
	},
    methods: {
    	change: function(e) {
    		this.$emit('chooseImage', e)
    	}
    }
}
</script>

<style scoped lang="sass">
	.upload
		width: 100%
		height: 100%
		background: url(../assets/cristal-mood-rain-rain-water-drops-wet-wet-glass-1366702-pxhere.com.jpg) center center no-repeat
		background-size: cover
	.wrapper
		display: flex
		flex-direction: column
		justify-content: flex-start
	.upload__header
		display: flex
		align-items: flex-end
		height: 80px
	.header
		display: flex
		align-items: baseline
		justify-content: flex-start
		flex-wrap: wrap
	.header__title
		margin-right: 20px
		font-size: 29px
		font-weight: 800
		text-transform: uppercase
	.header__subtitle
		font-size: 18px
		font-weight: 300
	.upload__content
	.content
	.content__input
		display: flex
		flex-wrap: wrap
		padding-top: 100px
	.content__input-hidden
		display: none
		visibility: hidden
	.content__input-label
		display: flex
		align-items: center
		justify-content: center
		width: 100%
		max-width: 260px
		height: 60px
		margin-right: 20px
		margin-bottom: 10px
		line-height: 1
		background-color: white
		border-left: 60px solid rgb(0, 160, 107)
		border-radius: 3px
		box-sizing: border-box
		text-transform: uppercase
		color: rgb(0, 160, 107)
		cursor: pointer
	.content__input-button
		display: flex
		align-items: center
		justify-content: center
		width: 180px
		height: 60px
		margin-bottom: 10px
		line-height: 1
		background-color: rgb(0, 160, 107)
		border: none
		border-radius: 3px
		font-family: 'Exo 2', sans-serif
		font-size: 16px
		box-sizing: border-box
		text-transform: uppercase
		color: white
		cursor: pointer
</style>