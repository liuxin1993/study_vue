<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="area">
				<div class="title border-topbottom">当前城市</div>
				<div class="wrapper-box">
					<div class="wrapper-button">
						<div class="button">北京</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="title border-topbottom">热门城市</div>
				<div class="wrapper-box">
					<div class="wrapper-button" v-for="item of hot" :key="item.id">
						<div class="button">{{item.name}}</div>
					</div>					
				</div>
			</div>
			<div class="area">
				<div v-for="(city, key) of cities" :key="key">
					<div class="title border-topbottom">{{key}}</div>
					<ul class="name-list">
						<li class="name" v-for="item of city" :key="item.id">{{item.name}}</li>						
					</ul>
				</div>				
			</div>
		</div>
	</div>
</template>

<script>
	import BScroll from 'better-scroll'
	export default {
		name:'CityList',
		props:{
			hot:Array,
			cities:Object
		},
		mounted () {
			this.scroll = new BScroll(this.$refs.wrapper)
		}
	}
</script>

<style lang="stylus" scoped>
	.list	
		position:absolute
		left:0
		top:1.66rem
		right:0
		bottom:0
		overflow:hidden
		.border-topbottom
			&:before
				border-color:#ddd	
			&:after
				border-color:#ddd	
		.title
			font-size:.28rem
			line-height:.5rem
			padding-left:.15rem
			color:#666
			background:#eee
		.wrapper-box
			padding:.1rem .3rem .1rem .1rem
			overflow:hidden
			background:#fff
			.wrapper-button
				width:33.33%
				float:left
				.button				
					text-align:center
					border:1px solid #ddd
					margin:.1rem
					font-size:0.28rem
					line-height:.4rem
		.name-list
			.name
				font-size:.26rem
				line-height:.66rem
				padding-left:.1rem
				color:#333
				border-bottom:1px solid #ddd
</style>