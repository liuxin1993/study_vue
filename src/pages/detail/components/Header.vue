<template>
	<div>
		<router-link tag="div" to="/" class="header-back" v-show="fixedShow">
			<span class="iconfont">&#xe624;</span>
		</router-link>
		<div class="detail-header" v-show="!fixedShow" :style="styl">
			城市选择
			<router-link tag="div" to="/" class="detail-fixed-back">
				<span class="iconfont">&#xe624;</span>
			</router-link>
		</div>
	</div>
</template>

<script>
	export default {
		name:'DetailHeader',
		data () {
			return {
				fixedShow:true,
				styl:{
					opacity:0
				}
			}
		},
		methods:{
			headerScroll(){
				let top = document.documentElement.scrollTop
				if(top > 60){
					let opacity = top/140
					opacity = opacity > 1 ? 1 : opacity
					this.styl = {
						opacity
					}
					this.fixedShow = false
				}else{
					this.fixedShow = true
				}
			}
		},
		activated(){
			window.addEventListener('scroll',this.headerScroll)
		},
		deactivated(){
			window.removeEventListener('scroll',this.headerScroll)
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header-back
		width:.8rem
		height:.8rem
		line-height:.8rem
		text-align:center
		background:#999
		color:#fff
		border-radius:50%
		position:absolute
		left:.2rem
		top:.2rem
	.detail-header
		height:$headerHeight
		line-height:$headerHeight
		background:$bgColor
		position:fixed
		left:0
		top:0
		right:0
		color:#fff
		font-size:.32rem
		text-align:center
		.detail-fixed-back
			color:#fff
			position:absolute
			left:.2rem
			top:0
			
		
</style>