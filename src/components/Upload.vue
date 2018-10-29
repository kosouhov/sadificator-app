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
						<input type="file" id="input" @change="change">
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Upload',
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
		background: url(../assets/rain-e833b50f2d_1920.jpg) center center no-repeat
		background-size: cover
	.wrapper
		display: flex
		flex-direction: column
		justify-content: space-between
	.upload__header
		display: flex
		align-items: flex-end
		height: 80px
	.header
		display: flex
		align-items: baseline
		justify-content: flex-start
	.header__title
		font-size: 29px
		font-weight: 800
		text-transform: uppercase
	.header__subtitle
		margin-left: 20px
		font-size: 18px
		font-weight: 300
</style>