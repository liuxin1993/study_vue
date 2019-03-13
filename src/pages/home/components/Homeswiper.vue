<template>
	<div class="wrapper">
		<swiper :options="swiperOption" class="swiper">
		    <!-- slides -->
		    <swiper-slide v-for="item of swiperList" :key="item.id">
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
		data () {
			return {
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				},
				swiperList:[
					{
						id:'001',
						imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/ad906cbe02849a504c4a4399741013a4.jpg_750x200_8ac64dcc.jpg'
					},{
						id:'002',
						imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/2df3ba0f23801d7ed5607f4767a18482.jpg_750x200_b4d6aa93.jpg'
					}
				]
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