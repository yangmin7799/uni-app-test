<template>
	<view class="content">
		<component :is="Page"/>
		<view  class="tabs">
			<view v-for="(tab,index) in tabs" :key="tab.name" class="tab" @click="handleTab(tab,index)">{{tab.name}}</view>
		</view>
	</view>
</template>

<script>
import List from "../list";
import Home from "../home";

	export default {
		components: {
			Home,
			List
		},
		data() {
			return {
				active: 0,
				tabs: [
					{
						name: "首页",
						component: "Home"
					},
					{
						name: "列表",
						component: "List"
					}
				]
			}
		},
		computed:{
			Page(){
				return this.tabs[this.active].component;
			}
		},
		onLoad() {

		},
		methods: {
			handleTab(tab,index){
				if(this.active === index) return;

				this.active = index;
			}
		}
	}
</script>

<style lang="scss">
	.content {
		text-align: center;
		height: 100vh;
		position: relative;
		.tabs{
			position: fixed;
			left: 0;
			bottom: 0;
			width: 100%;
			height: 8%;
			display: flex;
			justify-content: space-around;
			align-items: center;
			background-color: #8abff5;
			color: #fff;
		}
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
