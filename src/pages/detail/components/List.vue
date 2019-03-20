<template>
	<div>
		<div class="list" v-for="(item, index) of dataList" :key="index">
			<div class="title">
				<span class="title-img"></span>
				{{item.title}}
			</div>
			<div class="list1" v-if="item.childer">
				<detail-list :dataList="item.childer"></detail-list>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name:"DetailList",
		props:{
			dataList:Array
		}
	}
</script>

<style lang="stylus" scoped>
	.list1
		padding-left:.3rem
	.title
		font-size:.4rem
		position:relative
		padding-left:.6rem
		line-height:.7rem
		line-height:.7rem
		.title-img
			display:block
			width:.36rem
			height:.36rem
			position:absolute
			left:.2rem
			top:.2rem
			background:url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
			background-size: .4rem 3rem
			margin-right:.1rem
</style>