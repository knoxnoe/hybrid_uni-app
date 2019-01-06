<template>
	<view class="content">
		<view class="state"></view>
		<view class="noe_content">
			<image class="bg_top" src="../../static/images/bg_top.png"></image>
			<view class="sub_content">
				<view class="noe_fixed">
					<image class="bg_fixed" src="../../static/images/bg_fixed.png"></image>
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
				</view>
				<view class="noe_scroll">
					<view class="noe_sw">
						<swiper :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
							<swiper-item v-for="item in itemList">
								<image class="sw" v-bind:src="item"></image>
							</swiper-item>
						</swiper>
					</view>
					<view class="noe_type">
						<view class="type" v-for="item in typesList">
							<image v-bind:src="item.src"></image>
							<text>{{item.type}}</text>
						</view>
					</view>
					<view class="noe_country">
						<view class="coun_title">
							<image src="../../static/images/dec.png"></image>
							<text>发现同城好店</text>
							<image src="../../static/images/dec.png"></image>
						</view>
					</view>
				</view>
				<view class="noe_hswiper">
					<scroll-view class="top-menu-view" scroll-x="true" :scroll-left="scrollLeft">
						<block v-for="(menuTab,index) in menuTabs" :key="index">
							<view class="menu-one-view" v-bind:id="'tabNum'+index">
								<image class="img" src="../../static/images/test.png"></image>
								<view class="circle"></view>
								<text>KNOX NOE男装</text>
								<!--<view :class="[currentTab==index ? 'menu-one-act' : 'menu-one']">
									 <view class="menu-one-txt">
										{{menuTab.name}}
									</view> 
								</view>-->
							</view>
						</block>
					</scroll-view>
				</view>
				<view class="noe_push">
					<view class="coun_title">
						<image src="../../static/images/dec.png"></image>
						<text>为你推荐</text>
						<image src="../../static/images/dec.png"></image>
					</view>
					<view class="main">
						<view class="view1" style="background-color: red;"></view>
						<view class="view2" style="background-color: green;"></view>
						<view class="view1" style="background-color: pink;"></view>
						<view class="view2" style="background-color: blue;"></view>
						<view class="view1" style="background-color: orange;"></view>
						<view class="view2" style="background-color: #DDDDDD;"></view>
					</view>
				</view>
			</view>
		</view>
		<view class="noe_tab"></view>
	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				scrollLeft: 0,
				isClickChange: false,
				currentTab: 0,
				menuTabs: [{
					name: '政策咨询'
				}, {
					name: '就业分配'
				}, {
					name: '战友互助'
				}, {
					name: '趣味杂谈'
				}, {
					name: '怀旧时光'
				}, {
					name: '军旅生活'
				}],
				itemList: [
					'../../static/images/sw1.png',
					'../../static/images/sw1.png',
					'../../static/images/sw1.png'
				],
				typesList: [{
					src:'../../static/images/type1.png',
					type:'女装'
				},{
					src:'../../static/images/type2.png',
					type:'潮鞋'
				},{
					src:'../../static/images/type3.png',
					type:'内搭'
				},{
					src:'../../static/images/type4.png',
					type:'配饰'
				},{
					src:'../../static/images/type5.png',
					type:'男装'
				}],
				indicatorDots: false,
				autoplay: false,
				interval: 5000,
				duration: 1000
			}
		},
		onLoad() {

		},
		methods: {
		}
	}
</script>

<style>
	.noe_tab{
		width: 100%;
		height: 50px;
		background-color: red;
		position: fixed;
		bottom:0;
	}
	
	
	
	.noe_push{
		background-color: #FFFFFF;
		text-align: center;
		overflow: hidden;
		padding-top: 60upx;
	}
	.noe_push .main{
		
	}
	.noe_push .main view{
		margin-top:20upx;
	}
	.noe_push .main .view1{
		width: 45%;
		height: 200px;
		float: left;
	}
	.noe_push .main .view2{
		width: 45%;
		height: 200px;
		float: right;
	}
	.noe_hswiper{
		padding-top: 30upx;
		background-color: #FFFFFF;  /*遮罩bg-top */
	}
	.top-menu-view {
		display: flex;
		white-space: nowrap;
		width: 100%;
		background-color: #FFFFFF;
		/* 在这里设置导航条高度 */
	}
	 
	.top-menu-view .menu-one-view {
		width: 200px;
		height: 200px;
		background: #ffffff;
		display: inline-block;
		white-space: nowrap;
		margin-right: 10px;
		border-radius: 5px;
		box-shadow: 0px 5px 10px #ddd;
		text-align: center;
	}
		
	.top-menu-view .menu-one-view .img{
		width: 200px;
		height: 100px;
	}
	.top-menu-view .menu-one-view .circle{
		width: 80px;
		height: 80px;
		border-radius: 50%;
		background: red;
		margin: -40px auto 10px;
		position: relative;
	}
	.top-menu-view .menu-one-view text{
		font-size: 16px;
	}
	.top-menu-view .menu-one-view .menu-one {
		/* 在这里写 单个按钮样式 */
		margin-left: 25upx;
		margin-right: 25upx;
		position: relative;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	 
	.top-menu-view .menu-one-view .menu-one .menu-one-txt {
		height: 40upx;
		font-size: 28upx;
		font-weight: 400;
		color: rgba(154, 154, 154, 1);
		line-height: 40upx;
	}
	 
	.top-menu-view .menu-one-view .menu-one .menu-one-bottom {
		position: absolute;
		bottom: 0;
		width: 100%;
	}
	 
	.top-menu-view .menu-one-view .menu-one .menu-one-bottom .menu-one-bottom-color {
		width: 60%;
		height: 4upx;
	}
	 
	.top-menu-view .menu-one-view .menu-one-act {
		/* 在这里写 单个按钮样式 */
		margin-left: 25upx;
		margin-right: 25upx;
		position: relative;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	 
	.top-menu-view .menu-one-view .menu-one-act .menu-one-txt {
		height: 40upx;
		font-size: 28upx;
		font-weight: 400;
		color: rgba(0, 170, 255, 1);
		line-height: 40upx;
	}
	 
	.top-menu-view .menu-one-view .menu-one-act .menu-one-bottom {
		position: absolute;
		bottom: 0;
		width: 100%;
		display: flex;
		justify-content: center;
	}
	 
	.top-menu-view .menu-one-view .menu-one-act .menu-one-bottom .menu-one-bottom-color {
		width: 60%;
		height: 4upx;
		background: rgba(0, 170, 255, 1);
	}
	
	.noe_country{
		margin-top:52upx;
		text-align: center;
	}
		
	.coun_title{
		display: inline-flex;
		justify-content: space-between;
	    align-items: baseline;
	}
	.coun_title text{
		margin:0 40upx;
	}
	.coun_title image{
		width:40upx;
		height: 24upx;
	}
	.coun_title image:nth-child(1){
		-moz-transform:scaleX(-1);
		-webkit-transform:scaleX(-1);
		-o-transform:scaleX(-1);
		transform:scaleX(-1);
	}
	
	
	.noe_type{
		display: flex;
		justify-content: space-around;
		margin-top:60upx;
	}
	.noe_type .type{
		display: flex;
		flex-direction:column;
		text-align: center;
	}
	.noe_type .type image{
		width: 40px;
		height: 40px;
	}
	
	
	
	
	
	.state{
		width: 100%;
		height: 42upx;
		background-color: #7455ff;
		position: fixed;
		top: 0;
		z-index: 1;
	}
	.bg_top{
		width:100%;
		position: absolute;
		z-index: -5;
		margin-top:-1upx;
		height: 480upx;
		position: fixed;
	}
	.bg_fixed{
		position: absolute;
		width: 100vw;
		height: 130px;
		margin-left: -6%;
		margin-top: -1px;
	}
	.noe_content{
		margin-top: 21px;
	}
	.sub_content{
		width: 90%;
		margin:0 auto;
		font-size: 14px;
		font-family: san-serf;
		overflow: hidden;
		padding-bottom: 50upx;
	    background: #ffffff;
	}
	.noe_fixed{
		position: fixed;
		width: 90%;
		z-index: 2;
	}
	.noe_scroll{
		position: relative;
		background-color: #FFFFFF;  /*遮罩bg-top */
	}
	.noe_nav{
		padding-top: 50upx;
		width:100%;
		display: flex;
		justify-content: space-between;
		position: relative;
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
		padding-top: 40upx;
	}
	.noe_search input{
		background-color: #ffffff;
		border-radius: 200upx;
		padding-left: 10upx;
		height: 80upx;
		line-height: 80upx;
		position: relative;
	}
	.noe_sw{
		margin-top:260upx;
		box-shadow: 0px 7px 30px #ddd;
	}
	.noe_sw image{
		width:100%;
		height: 100%;
	}
</style>
