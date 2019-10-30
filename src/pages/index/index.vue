<template>
	<view class="content">
		<view v-if="start">
			<view class="image-holder">
				<image class="head-image left-image" src="/static/daisy.jpg" />
				<view class="image-gap" />
				<image class="head-image right-image" src="/static/wallace.jpg" />
			</view>
		</view>
		<view class="txt-holder">
			<view class="txt" v-for="(t, idx) in txt" :key="idx">{{t}}</view>
		</view>
	</view>
</template>

<script>
const text = `
October 30th, 2019

we start writting wechat program
it should be fun

~ Daisy & Wallace ~
`

export default {
	data()
	{
		return {
			txt: [],
			start: false,
		}
	},

	async onLoad()
	{
		setTimeout(() => this.start = true, 500)
		await sleep(500)
		this.showText()
	},

	methods:
	{
		async showText()
		{
			for (let t of text.split('\n'))
			{
				this.txt = [ ...this.txt, t ]
				if (t)
				{
					await sleep(1000)
				}
			}
		},
	},
}

function sleep(milliseconds)
{
	return new Promise((res) => setTimeout(res, milliseconds))
}
</script>

<style scoped>
.content {
	position: fixed;
	width: 100%;
	height: 100%;
	display: flex;
	/* align-items: center; */
	margin-top: 280upx;
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

.left-image {
	animation: leftrotate 1s;
	animation-fill-mode: forwards;
}

.right-image {
	animation: rightrotate 1s;
	animation-fill-mode: forwards;
}

.txt-holder {
	position: fixed;
	top: 500upx;
	width: 100%;
	display: flex;
	justify-content: center;
	flex-direction: column;
	padding: 40upx;
}

.txt {
	text-align: center;
	font-size: 36upx;
	color: #6b6b6d;
	animation: fadeshow 2s;
	animation-fill-mode: forwards;
	height: 50upx;
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

@keyframes leftrotate {
	from {
		transform: rotate(-180deg);
	}
	to {
		transform: rotate(0deg);
	}
}

@keyframes rightrotate {
	from {
		transform: rotate(180deg);
	}
	to {
		transform: rotate(0deg);
	}
}
</style>
