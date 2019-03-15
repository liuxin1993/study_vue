<template>
	<div>
		<div class="search">
			<input v-model="wordkey" class="search-input" type="text" placeholder="输入城市名或拼音" />
		</div>
		<div class="lixt-conent" v-show="wordkey" ref="wrapper">
			<ul class="list">
				<li class="list-name" v-for="item of list" :key="item.id" @click="handCity(item.name)">{{item.name}}</li>
				<li class="list-ts list-name" v-show="hasNoData">未找到相应结果</li>
			</ul>
		</div>
	</div>
</template>

<script>
	import Bscroll from 'better-scroll'
	export default {
		name:'CitySearch',
		props:{
			cities:Object
		},
		data () {
			return {
				wordkey:'',
				list:[],
				timer:null
			}
		},
		watch:{
			wordkey () {
				if(this.timer){
					clearTimeout(this.timer)
				}
				if(!this.wordkey){
					this.list = []
					return
				}
				this.timer = setTimeout(()=>{
					const reslt = []
					for(let i in this.cities){
						this.cities[i].forEach((value)=>{
							if(value.spell.indexOf(this.wordkey) > -1 || value.name.indexOf(this.wordkey) > -1){
								reslt.push(value)
							}
						})
					}
					this.list = reslt
				},100)
			}
		},
		computed:{
			hasNoData () {
				return !this.list.length
			}
		},
		methods:{
			handCity(city){
				this.$store.commit('changeCity',city)
				this.$router.push('/')
			}
		},
		mounted () {
			this.scroll = new Bscroll(this.$refs.wrapper)
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.search
		background:$bgColor
		height:.6rem
		padding:.1rem
		.search-input
			width:100%
			padding:0 .1rem
			box-sizing:border-box
			line-height:.6rem
			height:.6rem
			overflow:hidden
			text-align:center
			font-size:.26rem
			color:#666
			border-radius:.1rem
	.lixt-conent
		position:absolute
		top:1.66rem
		left:0
		right:0
		bottom:0
		z-index:1
		background:#fff
		overflow:hidden
		.list-name
			line-height:.6rem
			padding-left:.2rem
			font-size:.28rem
			border-bottom:1px solid #ccc
			color:#666
</style>