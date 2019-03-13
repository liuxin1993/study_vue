<template>
	<div>
		<div class="recommend-tit">热销推荐</div>
		<div class="recommend-box" v-for="item of recommendList" :key="item.id">
			<img class="recommend-img" :src="item.imgUrl">
			<div class="recommend-box1">
				<div class="recommend-box1-tit">{{item.title}}</div>
				<div class="recommend-desc">{{item.desc}}</div>
				<div class="recommend-details">查看详情</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name:"HomeRecommend",
		data () {
			return {
				recommendList:[
					{
						id:'001',
						imgUrl:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
						title:'大连圣亚海洋世界',
						desc:'浪漫大连首站，浪漫的海洋主题公园'
					},{
						id:'002',
						imgUrl:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
						title:'大连圣亚海洋世界',
						desc:'浪漫大连首站，浪漫的海洋主题公园'
					},{
						id:'003',
						imgUrl:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
						title:'大连圣亚海洋世界',
						desc:'浪漫大连首站，浪漫的海洋主题公园'
					},{
						id:'004',
						imgUrl:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
						title:'大连圣亚海洋世界',
						desc:'浪漫大连首站，浪漫的海洋主题公园'
					}
				]
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/mixins.styl'
	.recommend-tit
		padding-left:.2rem
		line-height:.6rem
		font-size:.3rem
		background:#eee
		color:#000
		margin-top:.1rem
	.recommend-box
		padding:.2rem
		display:flex
		.recommend-img
			width:1.5rem
			height:1.5rem
		.recommend-box1
			flex:1
			min-width:0
			margin-left:.2rem
			.recommend-box1-tit
				font-size:.3rem
				line-height:.5rem
				ellipsis()
			.recommend-desc
				font-size:.22rem
				color:#999
				line-height:.5rem
				ellipsis()
			.recommend-details
				color:#fff
				padding:.1rem
				font-size:0.26rem
				background:#ff9300
				float:left
				border-radius:.1rem
</style>