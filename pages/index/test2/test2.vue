<template>
	<view>
		<input type="text"/>
		<button type="primary" @click="button1">隐藏软键盘</button>
		<button type="primary" @click="button2">监听键盘高度变化</button>
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
			},
			button2()
			{
				console.log("监听键盘高度变化");
				uni.onKeyboardHeightChange(function(res)
				{
					console.log("键盘高度变化：",res.height);
				})
			}
		},
	}
</script>

<style>
button{
	margin: 5px;
}
</style>
