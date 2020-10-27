<template>
<view class="content">
	<view class="text-area" style="position: relative;">
	<text class="title" style="position: absolute;" id="target">{{title}}</text>
	</view>
</view>
</template>
 
<script>
export default {
	data() {
		return {
			
		}
	},
	onLoad() {  //页面初始化执行,用户页面获取参数
		
	},
	onReady() { //页面初次渲染完毕执行
		this.getInfo()
	},
	methods: {
		getInfo() {

			// 注意：想要拿到元素实例，需要在实例已经挂载到页面上才可以
			const query = uni.createSelectorQuery().in(this);
			query.select('#target').boundingClientRect(data => {
				console.log(data);
			}).exec();

		}
	}
}
</script>
