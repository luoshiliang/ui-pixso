<template>
	<view class="all">
		<view class="head">
			<view class="navtior">
				<view class="back">
					<img class="backImg" src="../../static/uiIcon/back.png" alt="">
					<text>Back</text>
				</view>
				<view class="navIcon">
					<img src="../../static/uiIcon/more.png" alt="">
					<img src="../../static/uiIcon/search.png" alt="">
					<img src="../../static/uiIcon/shop.png" alt="">
				</view>
			</view>
			<view class="info">
				<view class="info-left">
					<view class="textLeft">
						<img src="../../static/uiIcon/mdl.png" alt="">
					</view>
					<view class="textRight">
						<view>McDonadl's</view>
						<view class="textRightBot">
							<img style="width: 25rpx;height: 25rpx;" src="../../static/uiIcon/posi.png" alt="">
							<view class="">
								Bramlea & Sandalwood
							</view>
						</view>
					</view>
				</view>
				<view class="info-right">
					<img class="tongImg rightImg" src="../../static/uiIcon/like.png" alt="">
				</view>
			</view>
		</view>
		<view class="tabbarNav">
			<view class="navItem" :class="nowItem == index ? 'on' : ''" v-for="(item,index) in tabbarList"
				:key="item.id" @click="changeItem(index)">
				{{item.name}}
			</view>
		</view>
		<view class="" v-if="nowItem == 0">
			我是空的哦......
		</view>
		<view class="contai" v-else-if="nowItem == 1">
			<view class="contai-top">
				<view class="topText textOn">
					Today's Deals
				</view>
				<view class="topText">
					Burger Meals
				</view>
				<view class="topText">
					chicken & Fish
				</view>
			</view>
			<view class="contai-bottom">
				<view class="botItem" v-for="(item,index) in shopItemList" :key="item.id">
					<view class="botLeft">
						<img :src="item.imgUrl" alt="">
						<view class="botCenter">
							<view class="">
								{{item.name}}
							</view>
							<view class="cerBot">
								<view class="botLef">
									${{item.hisPri}}
								</view>
								<view class="botRig">
									${{item.nowPri}}
								</view>
							</view>
						</view>
					</view>
					<view class="botRight">
						<img src="../../static/uiIcon/rightIcon.png" alt="">
					</view>
				</view>
			</view>
		</view>
		<view v-else>
			我是空的哦
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				nowItem:1,
				tabbarList: [{
						id: 0,
						name: 'BrealMenu',
					},
					{
						id: 1,
						name: 'Lunch&Dinner'
					},
					{
						id: 2,
						name: 'Onvringht'
					}
				],
				shopItemList: []
			}
		},
		methods: {
			changeItem(index){
				this.nowItem = index
			}
		},
		onLoad() {
			this.shopItemList = [{
						id: 0,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 1,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 2,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 3,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 4,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 5,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 6,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 7,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 8,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},
					{
						id: 9,
						name: 'Classic',
						imgUrl: '../../static/uni.png',
						hisPri: '2.59',
						nowPri: '3.59'
					},]
		}
	}
</script>

<style>
	.botLef {
		text-decoration: line-through;
	}

	.cerBot {
		display: flex;
	}

	.botCenter {
		margin-left: 20rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.botRig {
		margin-left: 20rpx;
		color: deepskyblue;
	}

	.botRight img {
		width: 100rpx;
		height: 100rpx;
	}

	.botLeft {
		display: flex;
	}

	.botLeft img {
		width: 120rpx;
		height: 120rpx;
	}

	.botItem {
		margin-top: 30rpx;
		border-bottom: 1px solid #ccc;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 30rpx 30rpx;
	}

/* 	.contai {
		padding: 0 20rpx;
	} */

	.contai-top {
		display: flex;
		justify-content: space-between;
		padding: 0 20rpx;
		margin-top: 30rpx;
	}

	.textOn {
		color: white;
		background-color: black !important;
	}

	.topText {
		padding: 20rpx 10rpx;
		box-sizing: border-box;
		border-radius: 100rpx;
		background-color: #ccc;
	}

	.on {
		border-bottom: 3px solid black;
		color: rgba(0, 0, 0, 1) !important;
	}

	.navItem {
		margin: 0 30rpx;
		height: 100rpx;
		line-height: 100rpx;
		color: rgba(0, 0, 0, 0.1);
	}

	.tabbarNav {
		display: flex;
		align-items: center;
		height: 100rpx;
		background-color: rgba(0, 0, 0, 0.1);
		margin: 10rpx 0;
		padding: 0 20rpx;
		box-sizing: border-box;
	}

	.textRightBot {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.info-left {
		display: flex;
		justify-content: space-between;
	}

	.textRight {
		margin-left: 20rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.rightImg {
		width: 100rpx;
		height: 100rpx;
	}

	.textLeft {
		background-color: red;
		width: 100rpx;
		height: 100rpx;
		border-radius: 50%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.textLeft img {
		width: 80rpx;
		height: 80rpx;
	}

	.info {
		margin: 60rpx 0;
		display: flex;
		justify-content: space-between;
	}

	.navtior {
		width: 99%;
		display: flex;
		justify-content: space-between;
		padding: 0 10rpx;
		box-sizing: border-box;
	}

	.navIcon {
		display: flex;
		justify-content: space-around;
		align-items: center;
	}

	.navIcon img {
		width: 50rpx;
		height: 50rpx;
		margin: 0 20rpx;
	}

	.all {
		width: 100%;
		padding: 20rpx 0;
		background-color: white;
	}

	.head {
		width: 100%;
		padding: 0 30rpx;
		box-sizing: border-box;
	}

	.backImg {
		width: 50rpx;
		height: 50rpx;
		margin-right: 10rpx;
	}

	.back {
		display: flex;
		align-items: center;
	}
</style>