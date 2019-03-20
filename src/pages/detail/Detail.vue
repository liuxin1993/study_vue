<template>
	<div class="detail">
		<detail-banner></detail-banner>
		<detail-header></detail-header>
		<detail-list :dataList="list"></detail-list>
	</div>
</template>

<script>
	import DetailBanner from './components/Banner'
	import DetailHeader from './components/Header'
	import DetailList from './components/List'
	export default {
		name:'Detail',
		components:{
			DetailBanner,
			DetailHeader,
			DetailList
		},
		data () {
			return {
				list:[
					{
						title:'儿童票1',
						childer:[
							{
								title:'儿童票1-1',
								childer:[
									{
										title:'儿童票1-2'
									}
								]
							},
							{
								title:'儿童票1-1',
							}
						]
					},{
						title:'儿童票1'
					},{
						title:'儿童票1'
					}
				]
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.detail
		height:50rem
</style>