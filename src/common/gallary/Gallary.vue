<template>
	<div class="contain" @click="handleClick">
		<div class="wrapper">
			<swiper :options="swiperOption">
			    <swiper-slide v-for="(item, index) of imgs" :key="index">
			    	<img class="gallary-img" :src="item" />
			    </swiper-slide>
			    <div class="swiper-pagination" slot="pagination"></div>
			 </swiper>
		</div>
	</div>
</template>

<script>
	export default {
		name:'Gallary',
		props:{
			imgs:Array
		},
		data () {
			return {
				swiperOption:{
					pagination:'.swiper-pagination',
					paginationType:'fraction',
					observeParents:true,
					observer:true
				}
			}
		},
		methods:{
			handleClick(){
				this.$emit('changeGallary')
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.contain>>>.swiper-container
		overflow:inherit
	.contain
		display:flex
		flex-direction:column
		justify-content:center
		position:fixed
		top:0
		bottom:0
		left:0
		right:0
		background:#000
		.gallary-img
			width:100%
		.swiper-pagination
			color:#fff
			bottom:-1rem
		
			
			
</style>