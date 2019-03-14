<template>
	<div class="search">
		<input class="search-input" type="text" placeholder="输入城市名或拼音" />
	</div>
</template>

<script>
	export default {
		name:'CitySearch'
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.search
		background:$bgColor
		height:.6rem
		padding:.1rem
		.search-input
			width:100%
			padding:0 .1rem
			box-sizing:border-box
			line-height:.6rem
			height:.6rem
			overflow:hidden
			text-align:center
			font-size:.26rem
			color:#666
			border-radius:.1rem
</style>