<template>
	<div>
		<home-header :city="city"></home-header>
		<home-swiper :list="swiperList"></home-swiper>
		<home-icons :list="iconList"></home-icons>
		<home-recommend :list="recommendList"></home-recommend>
		<home-weekend :list="weekendList"></home-weekend>
	</div>
</template>

<script>
	import HomeHeader from './components/Homeheader'
	import HomeSwiper from './components/Homeswiper'
	import HomeIcons from './components/Homeicons'
	import HomeRecommend from './components/Homerecommend'
	import HomeWeekend from './components/Homeweekend'
	import axios from 'axios'
	export default{
		name:'Home',
		data () {
			return {
				city:'',
				swiperList:[],
				iconList:[],
				recommendList:[],
				weekendList:[]
			}
		},
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend,
			HomeWeekend
		},
		methods:{
			getHomeInfo(){
				axios.get('/static/mock/index.json').then(this.getHomeInfoSucc)
			},
			getHomeInfoSucc(res){
				res = res.data
				if(res.ret&&res.data){
					const data = res.data
					this.city = data.city
					this.swiperList = data.swiperList
					this.iconList = data.iconList
					this.recommendList = data.recommendList
					this.weekendList = data.weekendList
				}
			}
		},
		mounted(){
			this.getHomeInfo()
		}
	}
</script>

<style>
</style>