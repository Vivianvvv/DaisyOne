<template>
	<view class="content">	
		<view class="kuang">
			<view class="line-top">
				<view class="log-item">
					<image class="yuwanlog" src="/static/yuwanlog.png" />
				</view>
				<view class="menu-text">首页</view>
				<view class="menu-text">游戏资料</view>
				<view class="menu-text">用户中心</view>
		   </view>
		   <view class="login-text">
			   <view class="dash-item">
			      <view class="dash1"></view>登录  <image class="yuwanlogin" src="/static/yuwanlogin.png" /> 
		       </view>
				<view class="conten-item">
					<input v-model="name" type="text" placeholder="    请输入您的账号" />
				</view>
				<view class="conten-item">
					<input v-model="password" type="password" placeholder="    请输入密码" />
				</view> 
				<button class="submit" @click="loginSuccess">登录</button>
				<view class="dash2"></view>
		   </view>
		   <view class="mail-item">
			   <image class="mail-image" src="/static/yuwanmail.png" />
		   </view>
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
   width: 700upx;
   height: 1150upx; 
}

.line-top{
	display: flex;
	flex-direction: row;
	font-size: 36upx;
    color: rgba(83, 83, 83, 0.8);
	margin: 20upx 0 ;

}

.yuwanlog{
	width: 190upx;
	height: 120upx;
}

.menu-text {
	margin: 20upx 25upx;
}

.login-text{
	margin: 70upx 50upx;
}

.dash-item{
	display: flex;
	flex-direction: row;
	margin: 50upx 40upx;
	font-size: 48upx;
	color: #6d6d6d;
	position: relative;
}

.dash1 {
	height: 1upx;
	width: 150upx;
	background-color: rgba(206, 203, 203, 0.8);
	margin: 30upx ;
}

 .yuwanlogin {
	margin-top: 5upx;
	margin-right:10upx;
	width: 210upx;
	height: 200upx;
	position: absolute;
	top: -125upx;
	right: -10upx;
} 

.conten-item {
	display: flex;
	margin: 50upx;
}

.submit {	
	position: 	fixed;
	display: flex;
	justify-content: center;
	align-items: center;
	margin-left: 100upx;
	width: 400upx;
	height: 70upx;
	color: white;
	background-color: rgb(5, 175, 218)
}

.conten-item input{
	border-radius: 10upx;
	box-shadow: 0 0 5upx rgba(128, 126, 126, 0.692);
	width: 600upx;
	height: 70upx;
}

.dash2 {
	height: 1upx;
	width: 520upx;
	background-color:rgba(206, 203, 203, 0.8);
	margin: 180upx 40upx 0;
}

.mail-item{
	margin-left: 200upx ;
}

.mail-image{
	width: 300upx;
	height: 350upx;
}

</style>
