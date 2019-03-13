<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icons></home-icons>
	</div>
</template>

<script>
	import HomeHeader from './components/Homeheader'
	import HomeSwiper from './components/Homeswiper'
	import HomeIcons from './components/Homeicons'
	export default{
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons
		}
	}
</script>

<style>
</style>