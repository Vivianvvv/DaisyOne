<template>
	<view class="content">
		<view>
			<view class="image-holder">
				<image class="head-image" src="/static/daisy.jpg" />
				<view class="image-gap" />
				<image class="head-image" src="/static/wallace.jpg" />
			</view>
			<view class="title-holder">
				<view class="title" v-for="(t, idx) in title" :key="idx">{{t}}</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data()
	{
		return {
			title: [ '~ Daisy & Wallace ~' ],
		}
	},

	onLoad()
	{
		setTimeout(() => {
			this.title = [ ...this.title, 'is here' ]
		}, 1000)
	},

	methods:
	{

	}
}
</script>

<style>
.content {
	position: fixed;
	width: 100%;
	height: 100%;
	display: flex;
	/* align-items: center; */
	margin-top: 400upx;
	justify-content: center;
}

.image-holder {
	display: flex;
	flex-direction: row;
	margin-top: 200upx auto;
}

.image-gap {
	width: 750upx;
	animation: small 1s ease-out;
	animation-fill-mode: forwards;
}

.head-image {
	height: 200upx;
	width: 200upx;
	border-radius: 100upx;
}

.title-holder {
	position: relative;
	display: flex;
	justify-content: center;
	flex-direction: column;
	padding: 40upx;
}

.title {
	text-align: center;
	font-size: 36upx;
	color: #8f8f94;
	animation: fadeshow 1.5s;
	animation-fill-mode: forwards;
}

@keyframes small {
	from {
		width: 750upx;
	}
	to {
		width: 40upx;
	}
}

@keyframes fadeshow {
	from {
		opacity: 0;
	}
	to {
		opacity: 1;
	}
}
</style>
