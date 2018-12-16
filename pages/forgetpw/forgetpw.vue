<template>
    <view class="content">
		<view class="nav">
			<image class="nav-back" src="../../static/back.png" @tap="back"></image>
			<!-- <image class="nav-logo" src="../../static/xungou.png"></image> -->
		</view>
        <view class="input-group">
            <view class="input-row border">
                <text class="title">手机号</text>
                <input type="text" v-model="account" placeholder="请输入账号" placeholder-style="color:#fff;">
            </view>
            <view class="input-row">
                <text class="title">验证码</text>
                <input class="checkinput" type="text">
				<text class="checkpic">获取验证码</text>
            </view>
        </view>
		<view class="footer">
			<image src="../../static/logo.png"></image>
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
    		},
			initPosition() {
					/**
					* 使用 absolute 定位，并且设置 bottom 值进行定位。软键盘弹出时，底部会因为窗口变化而被顶上来。
					* 反向使用 top 进行定位，可以避免此问题。
					*/
					this.positionTop = uni.getSystemInfoSync().windowHeight - 100;
			}
    	},
		onLoad() {
			this.initPosition();
			// this.initProvider();
		}
    }
</script>

<style>
	@import "../../common/login.css";
	
	.checkpic{
		border: 2px solid #fff;
		height: 35px;
		color: #fff;
		line-height: 35px;
		text-align: center;
		font-size: .9em;
		border-radius: 5px;
		position: absolute;
		z-index: 3;
		background-color: #ffe25a;
		right: 13%;
		padding: 0 15px;
		box-sizing: border-box;
	}
	.checkpic:before{
		content: " ";
		width: 10px;
		height: 35px;
		position: absolute;
		left: -12px;
		background-color: #FFE25A;
	}
	.checkpic:after{
		content: " ";
		width: 40upx;
		height: 70upx;
		position: absolute;
		margin-left:17px;
		background-color: #FFE25A;
	}
	.btn-row{
		margin-top: 8.99%;
		margin-bottom: 7.5vh;
	}
	.footer{
		margin-top:40vh;
		text-align: center;
	}
	.footer image{
		width: 200upx;
		height: 64upx;
	}
</style>
