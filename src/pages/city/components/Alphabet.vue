<template>
	<ul class="list">
		<li class="name" v-for="(city, key) of cities" :key="key">{{key}}</li>
	</ul>
</template>

<script>
	export default {
		name:'CityAlphabet',
		props:{
			cities:Object
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