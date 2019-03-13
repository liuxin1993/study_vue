<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
		<home-recommend></home-recommend>
		<home-weekend></home-weekend>
	</div>
</template>

<script>
	import HomeHeader from './components/Homeheader'
	import HomeSwiper from './components/Homeswiper'
	import HomeIcons from './components/Homeicons'
	import HomeRecommend from './components/Homerecommend'
	import HomeWeekend from './components/Homeweekend'
	export default{
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend,
			HomeWeekend
		}
	}
</script>

<style>
</style>