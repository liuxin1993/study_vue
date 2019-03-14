<template>
	<div class="header">
		<div class="header-left">
			<span class="iconfont">&#xe624;</span>
		</div>
		<div class="header-mind">
			<span class="iconfont">&#xe632;</span>
			输入城市/景点/游玩主题
		</div>
		<router-link to="/City">
			<div class="header-right">
				{{this.city}}
				<span class="iconfont city-icon">&#xe6aa;</span>
			</div>
		</router-link>
	</div>
</template>

<script>
	export default {
		name:'HomeHeader',
		props:{
			city:String
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		height:.86rem
		line-height:.86rem
		background:$bgColor
		display:flex
		color:#fff
		.header-left
			width:.62rem
			float:left
			text-align:center
		.header-mind
			flex:1
			margin-top:.12rem
			margin-left:.2rem
			line-height:.62rem
			height:.62rem
			background-color:#fff
			border-radius:.1rem
			color:#999
			padding-left:.2rem
		.header-right
			width:1.24rem
			float:right
			text-align:center
			color:#fff
			.city-icon
				margin-left:-.04rem
				font-size:.3rem
</style>