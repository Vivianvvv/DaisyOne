<template>
	<view class="content">
		<view class="kuang">
			<view class="conten-item">
				<view class="input_text">用户名</view><input v-model="name" type="text" placeholder="请输入用户名" />
			</view>
			<view class="conten-item">
				<view class="input_text">密码</view><input v-model="password" type="password" placeholder="请输入密码" />
			</view> 
			<button class="submit" @click="loginSuccess">登录</button>
		</view>
	</view>
</template>

<script>
export default {
	data(){
		return {
		   name : '',
		   password : '',
		}
	},

	methods : {
		loginSuccess(){        
           if(this.name === 'admin'&&this.password==='123456'){
               uni.redirectTo({url : '../index/index'});
		   }
		},
	}

	

}

</script>

<style scoped>
.content {
	position: 	fixed;
	display: flex;
	justify-content: center;
	align-items: center;
	width:100%;
	height: 100%;
}

.kuang {
   width: 600upx;
   border-radius: 45upx;
   box-shadow: 0 0 5upx rgba(128, 126, 126, 0.692);
   padding: 100upx 0 100upx; 
}

.conten-item {
	display: flex;
	margin: 50upx;

}

.input_text {
	margin: 0 10upx;
	text-align: right;
	width: 150upx;
}

.submit {
	width: 400upx;
	font-size: 45upx;
}

.conten-item input{
	border-bottom: 1upx solid #cccccc;
	width: 320upx;
}

</style>
