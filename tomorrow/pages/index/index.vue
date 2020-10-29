<template>
	<view>
		<today ref='cpn'></today>
	</view>
</template>

<script>
	import today from '../../components/index.vue'
	
	export default{
		data(){
			return {
				scrollTop: 0
			}
		},
		components:{
			today
		},
		methods:{
			
		},
		onPageScroll(e){
			var that = this;
			that.scrollTop = e.scrollTop;
			that.$refs.cpn.scroll(that.scrollTop);
		}
		
	}
</script>