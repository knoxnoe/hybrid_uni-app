<template>
    <view class="content">
		<view class="nav">
			<image class="nav-back" src="../../static/images/back.png" @tap="back"></image>
			<image class="nav-logo" src="../../static/xungou.png"></image>
		</view>
        <view class="input-group">
            <view class="input-row border">
                <text class="title">注册账号</text>
                <input type="text" placeholder="请输入账号" placeholder-style="color:#fff;">
            </view>
            <view class="input-row">
                <text class="title">设置密码</text>
                <input type="text"  placeholder="请输入密码" placeholder-style="color:#fff;">
				<image class="cansee" src="../../static/cansee.png"></image>
            </view>
			<view class="input-row">
				<text class="title">验证码</text>
				<input class="checkinput" type="text">
				<text class="checkpic">获取验证码</text>
			</view>
        </view>
        <view class="btn-row">
            <view class="primary" @tap="bindLogin">完成</view>
        </view>
    </view>
</template>

<script>
    export default{
		methods: {
			back(){
				uni.navigateBack({
					delta: 1
				});
			}
		}	
	}
</script>

<style>
	@import "../../common/login.css";
	.input-group{
		margin-top: 20vh;
	}
	.nav{
		overflow: hidden;
	}
	.checkpic{
		border: 2px solid #fff;
		height: 35px;
		color: #fff;
		line-height: 33px;
		text-align: center;
		font-size: .8em;
		border-radius: 5px;
		/* display: none; */
		position: absolute;
		z-index: 3;
		background-color: #4983ff;
		right: 13%;
		padding: 0 15px;
	    box-sizing: border-box;
		font-weight: lighter;
		font-family: sans-serif;
	}
	.checkpic:before{
		content: " ";
		width: 20upx;
		height: 70upx;
		position: absolute;
		left: -24upx;
		background-color: #4983ff;
	}
	.checkpic:after{
		content: " ";
		width: 40upx;
		height: 70upx;
		position: absolute;
		margin-left:34upx;
		background-color: #4983ff;
	}
	uni-input div{
		width:100%;
	}
	.cansee{
		height: 48upx;
		width: 48upx;
		margin-left: -48upx;
	}
	.btn-row{
		margin-top: 25vh;
	}
	.title{
		color:#577bff;
	}
</style>
