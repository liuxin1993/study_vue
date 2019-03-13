<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
		<home-recommend></home-recommend>
	</div>
</template>

<script>
	import HomeHeader from './components/Homeheader'
	import HomeSwiper from './components/Homeswiper'
	import HomeIcons from './components/Homeicons'
	import HomeRecommend from './components/Homerecommend'
	export default{
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend
		}
	}
</script>

<style>
</style>