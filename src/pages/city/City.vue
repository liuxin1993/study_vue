<template>
	<div>
		<city-header></city-header>
		<city-search :cities="cities"></city-search>
		<city-list :letter="letter" :cities="cities" :hot="hotCity"></city-list>
		<city-alphabet :cities="cities" @change="changeTxt"></city-alphabet>
	</div>
</template>

<script>
	import axios from 'axios'
	import CityHeader from './components/Header'
	import CitySearch from './components/Search'
	import CityList from './components/List'
	import CityAlphabet from './components/Alphabet'
	export default {
		name:'City',
		components:{
			CityHeader,
			CitySearch,
			CityList,
			CityAlphabet
		},
		data () {
			return {
				hotCity:[],
				cities:{},
				letter:''
			}
		},
		methods:{
			getCityInfo(){
				axios.get('/static/mock/city.json').then(this.getCityInfoSucc)
			},
			getCityInfoSucc(res){
				res = res.data
				if(res.ret&&res.data){
					const data = res.data
					this.hotCity = data.hotCities
					this.cities = data.cities
				}
			},
			changeTxt(letter){
				this.letter = letter
			}
		},
		mounted () {
			this.getCityInfo()
		}
	}
</script>

<style lang="stylus" scoped>
</style>