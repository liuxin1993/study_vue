<template>
	<div>
		<div class="weekend-tit">周末去哪儿</div>
		<div class="weekend-box" v-for="item of list" :key="item.id">
			<img class="weekend-img" :src="item.imgUrl">
			<div class="weekend-box1">
				<div class="img-title">{{item.title}}</div>
				<div class="img-desc">{{item.desc}}</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name:"HomeWeekend",
		props:{
			list:Array
		}
	}
</script>

<style lang="stylus" scoped>
	.weekend-tit
		padding-left:.2rem
		line-height:.5rem
		font-size:.3rem
		color:#000
		margin-bottom:.1rem
	.weekend-box
		padding: 0 .1rem
		.weekend-img
			width:100%
			height:auto
		.weekend-box1
			padding: .1rem .2rem
			.img-title
				font-size:.3rem
				color:#000
				line-height:.5rem
			.img-desc
				font-size:.24rem
				color:#666
				line-height:.3rem
</style>