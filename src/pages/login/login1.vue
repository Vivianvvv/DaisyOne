<template>
	<view class="login-form-holder">
		<view class="login-form">
			<view class="form-item">
				<view class="item-title">用户名</view>
				<input v-model="name" placeholder="请输入用户名" />
			</view>
			<view class="form-item">
				<view class="item-title">密码</view>
				<input v-model="password" type="password" placeholder="请输入密码" />
			</view>
			<button class="commit-btn" @click="show">登录</button>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			name: '',
			password: '',
		}
	},
	methods: {
		show() {
			console.log(`name: "${this.name}", password: "${this.password}"`)
		},
	}
}
</script>
<style scoped>
.login-form-holder {
	position: fixed;
	width: 100%;
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
}
.login-form {
	width: 600upx;
	border-radius: 20upx;
	box-shadow: 0 0 5upx #888888;
	padding: 100upx 0 100upx;
}
.form-item {
	display: flex;
	margin: 50upx;
}
.item-title {
	width: 120upx;
	margin: 0 20upx;
	text-align: right;
}
.commit-btn {
	width: 400upx;
}
.form-item input {
	border-bottom: 1px solid #ccc;
	width: 340upx;
}
</style>