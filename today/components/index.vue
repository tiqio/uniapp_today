<template>
	<view>	
		<view style="width: 100vw;position: fixed;top: 0;left: 0;z-index: 2;background: rgba(255, 255, 255, 0.8);-webkit-backdrop-filter: saturate(180%) blur(10px);
						backdrop-filter: saturate(180%) blur(5px);" v-bind:style="{height:naviBarHeight+'px'}" v-if="show_barline">
			<view style="width: 100%;" v-bind:style="{height:statusBarHeight+'px'}"></view>
			<view style="width: 100%;display: flex;justify-content: center;align-items: center;font-size: 40rpx;font-weight: bold;" 
				    v-bind:style="{top:statusBarHeight+'px',height:naviBarHeight-statusBarHeight+'px',opacity:naviBarOpacity}">
				今日
			</view>
			<view style="width: 100%;height: 1px; background-color: #c6c6c8;position: absolute;bottom: 0;left: 0;"></view>
		</view>
		<view style="height: 40px;"></view>
		<view style="font-size: 30px;">今日</view>
	</view>
</template>

<script>
	export default{
		name: 'today',
		data(){
			return {
				naviBarHeight: 40,
				statusBarHeight: 3,
				naviBarOpacity: 0,
				show_barline: false,	
				underTop: 0,
				underBottom: 0
			}
		},
		mounted(){
			var that = this;
			const query = uni.createSelectorQuery().in(this);
			query.select('#target').boundingClientRect(data => {
				that.underTop = data.top;
				that.underBottom = data.bottom;
				console.log(that.underTop);
				console.log(that.underBottom);
			}).exec();
		},
		onPageScroll: function(e) {
					// 页面滚动时执行
					// console.log(e.scrollTop);
					var that = this;
					var top = that.underTop - that.naviBarHeight;
					var bottom = that.underBottom - that.naviBarHeight;
					// console.log(top);
					// console.log(bottom);
					var distance = e.scrollTop;
					// console.log(distance);
					// 暂时先不引入screenWidth
					if (distance < top){
						this.naviBarOpacity = 0;
						this.show_barline=false;
					}
					else if (distance > bottom){
						this.show_barline=true;
						this.naviBarOpacity = 1;
					}
					else{
						this.show_barline=true;
						this.naviBarOpacity = (distance - top)/(bottom - top);
						// console.log(this.naviBarOpacity);
					}
				},

	}
</script>

<style>
	#target{
		font-size: 50px;
		display: flex;
		justify-content: center;
	}
</style>

 
