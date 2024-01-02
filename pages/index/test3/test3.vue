<template>
	<view>
		<input type="text"/>
		<button type="primary" @click="button1">隐藏软键盘</button>
		<button type="primary" @click="button2">监听键盘高度变化</button>
		<button type="primary" @click="button3">取消监听键盘高度变化</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				f:undefined,
			}
		},
		methods: {
			button1()
			{
				uni.hideKeyboard();
			},
			button2()
			{
				if(!this.f)
				{
					console.log("监听键盘高度变化");
					this.f=function(res)
					{
						console.log("键盘高度变化：",res.height);
					}
					uni.onKeyboardHeightChange(this.f)
				}
			},
			button3()
			{
				if(this.f)
				{
					console.log("取消监听键盘高度变化");
					uni.offKeyboardHeightChange(this.f);
					this.f=undefined;
				}
			}
		},
	}
</script>

<style>
button{
	margin: 5px;
}
</style>
