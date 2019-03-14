<template>
	<div class="icons">
		<swiper :options="swiperOption"> 
			<swiper-slide v-for="(page, index) of pages" :key="index">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgUrl">
					</div>
					<div class="icon-p">{{item.desc}}</div>
				</div>	
			</swiper-slide>
			 <div class="swiper-pagination" slot="pagination"></div>
		</swiper>
	</div>
</template>

<script>
	export default{
		name:'HomeIcons',
		props:{
			list:Array
		},
		data () {
			return {
				swiperOption:{
					autoplay:false,
					pagination:'.swiper-pagination'
				}
			}
		},
		computed:{
			pages () {
				const pages = [];
				this.list.forEach((item,index)=>{
					const page = Math.floor(index/8)
					if(!pages[page]){
						pages[page] = []
					}
					pages[page].push(item)
				})
				return pages
				
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.icons>>>.swiper-container
		overflow:hidden
		height:0
		padding-bottom:50%
	.icon
		position:relative
		width:25%
		height:0
		padding-bottom:25%
		float:left
		.icon-img
			position:absolute
			left:0
			top:0
			right:0
			bottom:.44rem
			padding:.1rem
			.icon-img-content
				height:100%
				margin:0 auto
				display:block
		.icon-p
			position:absolute
			left:0
			right:0
			bottom:0
			text-align:center
			line-height:.44rem
			height:.44rem
			color:$fontColor		
</style>