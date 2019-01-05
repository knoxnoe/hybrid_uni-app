<template>
	<view class="content">
		<view class="state"></view>
		<view class="noe_content">
			<image class="bg_top" src="../../static/images/bg_top.png"></image>
			<view class="sub_content">
				<view class="noe_nav">
					<view class="noe_pos">
						<image src="../../static/images/pos.png"></image><text>中国石油大学（华东）</text>
					</view>
					<view>
						<text>切换同城版</text>
					</view>
				</view>
				<view class="noe_search">
					<input placeholder="这是一个可以自动聚焦的input" />
				</view>
				<view class="noe_sw">
					<swiper :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
						<swiper-item v-for="item in itemList" :key="item">
							<image class="sw" v-bind:src="item"></image>
						</swiper-item>
					</swiper>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				itemList: [
					'../../static/images/sw1.png',
					'../../static/images/sw1.png',
					'../../static/images/sw1.png'
				],
				indicatorDots: false,
				autoplay: false,
				interval: 5000,
				duration: 1000
			}
		},
		onLoad() {

		},
		methods: {
			changeIndicatorDots: function (e) {
            this.indicatorDots = !this.indicatorDots
			},
			changeAutoplay: function (e) {
				this.autoplay = !this.autoplay
			},
			intervalChange: function (e) {
				this.interval = e.detail.value
			},
			durationChange: function (e) {
				this.duration = e.detail.value
			}
		}
	}
</script>

<style>
	.state{
		width: 100%;
		height: 42upx;
		background-color: #7455ff;
	}
	.bg_top{
		width:100%;
		position: absolute;
		z-index: -1;
		margin-top:-1upx;
		height: 480upx;
	}
	.sub_content{
		width: 90%;
		margin:0 auto;
		font-size: 14px;
		font-family: san-serf;
	}
	.noe_nav{
		padding-top: 50upx;
		width:100%;
		display: flex;
		justify-content: space-between;
	}
	.noe_nav view{
		display: inline-flex;
		vertical-align: top;
	}
	.noe_pos image{
		width: 20px;
		height: 25px;
		vertical-align: middle;
		margin-right: 10upx;
	}
	.noe_nav text{
		color:#FFFFFF;
	}
	.noe_search{
		margin-top: 40upx;
	}
	.noe_search input{
		background-color: #ffffff;
		border-radius: 200upx;
		padding-left: 10upx;
		height: 80upx;
		line-height: 80upx;
	}
	.noe_sw{
		margin-top:40upx;
	}
	.noe_sw image{
		width:100%;
		height: 100%;
	}
</style>
