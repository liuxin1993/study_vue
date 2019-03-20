<template>
	<div class="detail">
		<detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
		<detail-header></detail-header>
		<detail-list :dataList="list"></detail-list>
	</div>
</template>

<script>
	import DetailBanner from './components/Banner'
	import DetailHeader from './components/Header'
	import DetailList from './components/List'
	import axios from 'axios'
	export default {
		name:'Detail',
		components:{
			DetailBanner,
			DetailHeader,
			DetailList
		},
		data () {
			return {
				sightName:'',
				bannerImg:'',
				gallaryImgs:[],
				list:[]
			}
		},
		methods:{
			handleDetailInfo(){
				axios.get('./static/mock/detail.json',{
					params:{
						id:this.$route.params
					}
				}).then(this.getDetailInfoSucc)
			},
			getDetailInfoSucc(res){
				res = res.data
				if(res.ret&&res.data){
					const data = res.data
					this.sightName = data.sightName
					this.bannerImg = data.bannerImg
					this.gallaryImgs = data.gallaryImgs
					this.list = data.categoryList
				}
			}
		},
		mounted(){
			this.handleDetailInfo()
		}
	}
</script>

<style lang="stylus" scoped>
	.detail
		height:50rem
</style>