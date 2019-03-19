<template>
	<div>
		<div class="banner" @click="handleClick">
			<img class="banner-img" src="//img1.qunarzz.com/sight/p0/1412/77/cb5a5c0c47e96f6b42ce646cddf4af0d.water.jpg_600x330_17d4b9aa.jpg">
			<div class="banner-info">
				<div class="title">鸟巢(AAAAA景区)</div>
				<div class="number"><span class="iconfont">&#xe637;</span>6</div>
			</div>
		</div>
		<gallary :imgs="imgs" v-show="showGallary" @changeGallary="changeGallary"></gallary>
	</div>
</template>

<script>
	import Gallary from 'common/gallary/Gallary'
	export default {
		name:'DetailBanner',
		data () {
			return {
				imgs:['http://img1.qunarzz.com/sight/p0/1412/f7/73c43024f19e33c695b364ccea1db63b.water.jpg_r_800x800_9cc7ad8b.jpg','http://img1.qunarzz.com/sight/p0/1507/c9/eefaa23facb37ac4814e336070207804.water.jpg_r_800x800_c58340e6.jpg'],
				showGallary:false
			}
		},
		methods:{
			handleClick(){
				this.showGallary = true
			},
			changeGallary(){
				this.showGallary = false
			}
		},
		components:{
			Gallary
		}
	}
</script>

<style lang="stylus" scoped>
	.banner
		overflow:hidden
		height:0
		padding-bottom:55%
		position:relative
		color:#fff
		.banner-img
			width:100%
		.banner-info
			position:absolute
			left:0
			right:0
			bottom:0
			line-height:.8rem
			font-size:.4rem
			display:flex
			background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
			.title
				padding-left:.2rem
				flex:1
			.number
				padding:0 .2rem
</style>