<template>
	<view>
		<view style="width: 100vw;position: fixed;top: 0;left: 0;z-index: 2;background: rgba(255, 255, 255, 0.8);-webkit-backdrop-filter: saturate(180%) blur(10px);
						backdrop-filter: saturate(180%) blur(5px);" v-bind:style="{height:naviBarHeight+'px'}" v-if="show_barline">
			<view style="width: 100%;" v-bind:style="{height:statusBarHeight+'px'}"></view>
			<view style="width: 100%;display: flex;justify-content: center;align-items: center;font-size: 40rpx;font-weight: bold;" 
				    v-bind:style="{top:statusBarHeight+'px',height:naviBarHeight-statusBarHeight+'px',opacity:naviBarOpacity}">
				{{today}}
			</view>
			<view style="width:;100%;height: 1px; background-color: #c6c6c8;position: absolute;bottom: 0;left: 0;" ></view>
		</view>
		<view class="target"></view>
		<!-- :style="{margin-top: naviBarHeight+'px' -->
		<view class="today">{{today}}</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
		<view>测试语句</view>
	</view>
</template>

<script>
	export default{
		name: 'tomorrow',
		data(){
			return {
				statusBarHeight: 3,
				naviBarHeight: 40,
				show_barline: false,
				underTop: 0,
				underBottom: 0,
				naviBarOpacity: 0,
				scrollTop: 0
			}
		},
		props:['today'],
		mounted(){
			var that = this;
			const query = uni.createSelectorQuery().in(this);
			query.select('.target').boundingClientRect(data => {
				that.underTop = data.top;
				console.log(that.underTop);
			}).exec();
			query.select('.today').boundingClientRect(data => {
				that.underBottom = data.bottom;
				console.log(that.underBottom);
			}).exec();
		},
		methods:{
			scroll(scrollTop){
				// console.log(scrollTop);
				var that = this;
				var distance = scrollTop;
				if(distance < that.underTop){
					that.show_barline = false;
					that.naviBarOpacity = 0;
				}else if(distance > that.underBottom){
					that.show_barline = true;
					that.naviBarOpacity = 1;
				}else{
					that.show_barline = true;
					that.naviBarOpacity = (distance - that.underTop) / (that.underBottom - that.underTop);
				}
			}
		}
	}
</script>

<style>
	.target{
		width: 100vw;
		height: 200px;
		margin-top: 40px;
	}
	.today{
		font-size: 50px;
	}
</style>