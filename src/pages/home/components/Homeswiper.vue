<template>
	<div class="wrapper">
		<swiper :options="swiperOption" class="swiper"  v-if="show">
		    <!-- slides -->
		    <swiper-slide v-for="item of list" :key="item.id">
		    	<img class="swiper-img" :src="item.imgUrl" />
		    </swiper-slide>
		    <!-- Optional controls -->
		    <div class="swiper-pagination" slot="pagination"></div>
		 </swiper>
	</div>
</template>

<script>
	export default {
		name:'HomeSwiper',
		props:{
			list:Array
		},
		data () {
			return {
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				}
			}
		},
		computed:{
			show(){
				return this.list.length
			}
		}
	}
</script>

<style lang="stylus" scoped>
    .swiper>>>.swiper-pagination-bullet-active
    	background:#fff
    	.wrapper
    		height:0
    		padding-bottom:26.7%
    		overflow:hidden
    		background:#999
			.swiper-img
				width:100%
</style>