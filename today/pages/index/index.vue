<template>
	<view>
		<view style="width: 100vw;position: fixed;top: 0;left: 0;z-index: 2;background: rgba(255, 255, 255, 0.8);-webkit-backdrop-filter: saturate(180%) blur(10px);
						backdrop-filter: saturate(180%) blur(5px);" v-bind:style="{height:naviBarHeight+'px'}" v-if="show_barline">
			<view style="width: 100%;" v-bind:style="{height:statusBarHeight+'px'}"></view>
			<view style="width: 100%;display: flex;justify-content: center;align-items: center;font-size: 40rpx;font-weight: bold;" 
				    v-bind:style="{top:statusBarHeight+'px',height:naviBarHeight-statusBarHeight+'px',opacity:naviBarOpacity}">
				今日
			</view>
			<view style="width: 100%;height: 1px; background-color: #c6c6c8;position: absolute;bottom: 0;left: 0;" ></view>
		</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
		<view>测试代码</view>
	</view>
</template>

<script>
	export default{
		data(){
			return {
				naviBarHeight: 40,
				statusBarHeight: 3,
				naviBarOpacity: 1,
				screenWidth: 1,
				show_barline: true,	
			}
		},
		onPageScroll: function(e) {
					// 页面滚动时执行
					console.log(e.scrollTop);
					
					var distance = Number(e.scrollTop + this.naviBarHeight);
					// 暂时先不引入screenWidth
					if (distance < 200){
						this.naviBarOpacity = 0;
						this.show_barline=false;
					}
					else if (distance > 500){
						this.show_barline=true;
						this.naviBarOpacity = 1;
					}
					else{
						this.show_barline=true;
						this.naviBarOpacity = (distance -200)/(300);
					}
				},

	}
</script>
