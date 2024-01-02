<template>
	<view>
		<input type="text"/>
		<button type="primary" @click="button1">隐藏软键盘</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			button1()
			{
				uni.hideKeyboard();
			}
		}
	}
</script>

<style>

</style>
