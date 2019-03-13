<template>
	<div>
		<div class="weekend-tit">周末去哪儿</div>
		<div class="weekend-box" v-for="item of weekendList" :key="item.id">
			<img class="weekend-img" :src="item.imgUrl">
			<div class="weekend-box1">
				<div class="img-title">{{item.title}}</div>
				<div class="img-desc">{{item.desc}}</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name:"HomeWeekend",
		data () {
			return {
				weekendList:[
					{
						id:'001',
						imgUrl:'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
						title:'北京赏花好地方',
						desc:'乱花渐欲迷人眼，京城赏花大搜索'
					},{
						id:'002',
						imgUrl:'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
						title:'北京赏花好地方',
						desc:'乱花渐欲迷人眼，京城赏花大搜索'
					},{
						id:'003',
						imgUrl:'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
						title:'北京赏花好地方',
						desc:'乱花渐欲迷人眼，京城赏花大搜索'
					},{
						id:'004',
						imgUrl:'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
						title:'北京赏花好地方',
						desc:'乱花渐欲迷人眼，京城赏花大搜索'
					}
				]
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.weekend-tit
		padding-left:.2rem
		line-height:.5rem
		font-size:.3rem
		color:#000
		margin-bottom:.1rem
	.weekend-box
		padding: 0 .1rem
		.weekend-img
			width:100%
			height:auto
		.weekend-box1
			padding: .1rem .2rem
			.img-title
				font-size:.3rem
				color:#000
				line-height:.5rem
			.img-desc
				font-size:.24rem
				color:#666
				line-height:.3rem
</style>