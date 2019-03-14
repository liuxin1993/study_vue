<template>
	<div class="header">
		城市选择
		<router-link to="/">
			<div class="iconfont header-back">&#xe624;</div>
		</router-link>
	</div>
</template>

<script>
	export default {
		name:'CityHeader'
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		height:$headerHeight
		line-height:$headerHeight
		text-align:center
		font-size:.32rem
		background:$bgColor
		color:#fff
		position:relative
		.header-back
			width:.6rem
			position:absolute
			left:0
			top:0
			font-size:.4rem
			color:#fff
</style>