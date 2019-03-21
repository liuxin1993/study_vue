<template>
	<div>
		<div class="banner" @click="handleClick">
			<img class="banner-img" :src="bannerImg">
			<div class="banner-info">
				<div class="title">{{this.sightName}}</div>
				<div class="number"><span class="iconfont">&#xe637;</span>6</div>
			</div>
		</div>
		<fade-animate>
			<gallary :imgs="gallaryImgs" v-show="showGallary" @changeGallary="changeGallary"></gallary>
		</fade-animate>
	</div>
</template>

<script>
	import Gallary from 'common/gallary/Gallary'
	import FadeAnimate from 'common/fade/FadeAnimate'
	export default {
		name:'DetailBanner',
		props:{
			sightName:String,
			bannerImg:String,
			gallaryImgs:Array
		},
		data(){
			return{
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
			Gallary,
			FadeAnimate
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