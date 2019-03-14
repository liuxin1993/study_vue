<template>
	<div class="list">
		<div class="area">
			<div class="title border-topbottom">当前城市</div>
			<div class="wrapper">
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
			</div>
		</div>
		<div class="area">
			<div class="title border-topbottom">热门城市</div>
			<div class="wrapper">
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
				<div class="wrapper-button">
					<div class="button">北京</div>
				</div>
			</div>
		</div>
		<div class="area">
			<div class="title border-topbottom">A</div>
			<ul class="name-list">
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li><li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
			</ul>
			<div class="title border-topbottom">B</div>
			<ul class="name-list">
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li><li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
				<li class="name">阿拉尔</li>
			</ul>
		</div>
	</div>
</template>

<script>
	export default {
		name:'CityList'
	}
</script>

<style lang="stylus" scoped>
	.list	
		position:absolute
		left:0
		top:1.66rem
		right:0
		bottom:0
		overflow:hidden
		.border-topbottom
			&:before
				border-color:#ddd	
			&:after
				border-color:#ddd	
		.title
			font-size:.28rem
			line-height:.5rem
			padding-left:.15rem
			color:#666
			background:#eee
		.wrapper
			padding:.1rem .3rem .1rem .1rem
			overflow:hidden
			background:#fff
			.wrapper-button
				width:33.33%
				float:left
				.button				
					text-align:center
					border:1px solid #ddd
					margin:.1rem
					font-size:0.28rem
					line-height:.4rem
		.name-list
			.name
				font-size:.26rem
				line-height:.66rem
				padding-left:.1rem
				color:#333
				border-bottom:1px solid #ddd
</style>