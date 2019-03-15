<template>
	<ul class="list">
		<li class="name" v-for="item of letters" :ref="item" :key="item" @click="handleClick" @touchstart="touchStart" @touchmove="touchMove" @touchend="touchEnd">{{item}}</li>
	</ul>
</template>

<script>
	export default {
		name:'CityAlphabet',
		props:{
			cities:Object
		},
		data () {
			return {
				touchStatus:false,
				startY:0,
				timer:null
			}
		},
		updated () {
			this.startY = this.$refs['A'][0].offsetTop
		},
		computed:{
			letters(){
				const letters = []
				for(let i in this.cities){
					letters.push(i)
				}
				return letters
			}
		},
		methods:{
			handleClick(e){
				this.$emit('change',e.target.innerText)
			},
			touchStart(){
				this.touchStatus = true
			},
			touchMove(e){
				if(this.timer){
					clearTimeout(this.timer)
				}
				this.timer = setTimeout(()=>{
					if(this.touchStatus){
						var moveY = e.touches[0].clientY-83
						var index = Math.floor((moveY-this.startY)/20)
						if(index>=0 && index <this.letters.length){
							this.$emit('change',this.letters[index])
						}
					}
				},16)
			},
			touchEnd(){
				this.touchStatus = false
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.list
		overflow:hidden
		width:.4rem
		font-size:.3rem
		line-height:.4rem
		display:flex
		flex-direction:column
		justify-content:center
		position:absolute
		top:1.66rem
		right:0
		bottom:0
		.name
			text-align:center
</style>