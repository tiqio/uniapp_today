<template>
	<view>
		<today ref='cpn' today="自定义语句"></today>
	</view>
</template>

<script>
	import today from '../../components/today.vue'
	
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
			this.$refs.cpn.scroll(e.scrollTop);
		}
		
	}
</script>