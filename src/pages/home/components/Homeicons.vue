<template>
	<div class="icons">
		<swiper>
			<swiper-slide v-for="(page, index) of pages" :key="index">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgUrl">
					</div>
					<div class="icon-p">{{item.desc}}</div>
				</div>	
			</swiper-slide>
		</swiper>
	</div>
</template>

<script>
	export default{
		name:'HomeIcons',
		data () {
			return {
				iconList:[
					{
						id:'001',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
						desc:'景点门票'
					},{
						id:'002',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
						desc:'一日游'
					},{
						id:'003',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
						desc:'北京必游'
					},{
						id:'004',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
						desc:'溜娃儿'
					},{
						id:'005',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
						desc:'景点门票'
					},{
						id:'006',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
						desc:'一日游'
					},{
						id:'007',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
						desc:'北京必游'
					},{
						id:'008',
						imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
						desc:'溜娃儿'
					},{
						id:'009',
						imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/0334cf5430b9b5505fd79e2b8d7e8670.png',
						desc:'爬长城'
					}
				]
			}
		},
		computed:{
			pages () {
				const pages = [];
				this.iconList.forEach((item,index)=>{
					const page = Math.floor(index/8)
					if(!pages[page]){
						pages[page] = []
						console.log(pages[page])
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