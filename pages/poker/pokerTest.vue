<template>
	<view class="content">
	
		<view class="play3 palybox mybox">
			<view class="paperOperate clearfix">
				<!-- <view class="nopaper">
					<text>不出</text>
				</view> -->
				<view class="hit" @tap='testhit(0)'>
					<text>空 </text>
				</view>
				<view class="hit" @tap='testhit(1)'>
					<text>单张 </text>
				</view>
				<view class="hit" @tap='testhit(2)'>
					<text>对子 </text>
				</view>
				<view class="hit" @tap='testhit(3)'>
					<text>三张 </text>
				</view>
				<view class="hit" @tap='testhit(4)'>
					<text>三带一 </text>
				</view>
				<view class="hit" @tap='testhit(5)'>
					<text>三带二</text>
				</view>
				<view class="hit" @tap='testhit(6)'>
					<text>四带二 </text>
				</view>
				<view class="hit" @tap='testhit(7)'>
					<text>四带两队 </text>
				</view>
				<view class="hit" @tap='testhit(8)'>
					<text>顺子 </text>
				</view>
				<view class="hit" @tap='testhit(9)'>
					<text>连队 </text>
				</view>
				<view class="hit" @tap='testhit(10)'>
					<text>飞机 </text>
				</view>
				<view class="hit" @tap='testhit(11)'>
					<text>飞机带单 </text>
				</view>
				<view class="hit" @tap='testhit(12)'>
					<text>飞机带双 </text>
				</view>
				<view class="hit" @tap='testhit(13)'>
					<text>炸弹</text>
				</view>
				<view class="hit" @tap='testhit(14)'>
					<text>王炸</text>
				</view>

				<view class="surePaper" @tap='showcard()'>
					<text>出牌</text>
				</view>
			</view>

		</view>
		
	
	</view>
</template>

<script>
	
	import {requestUrl} from "../../util/common.js";
	export default {
		data() {
			return {
				play2: [],
				play3: [],
				play4: [],
				play2paper: [],
				play3paper: [
					{card: 16,cardvalue: "joker",checked: false,color: "hx",isHint: true,num: "16",src: "../../static/image/card/16.png",type: "hx"},
					{card: 17,cardvalue: "joker",checked: false,color: "ht",isHint: true,num: "joker",src: "../../static/image/card/17.png",type: "ht"},
					{card: 13,cardvalue: "K",checked: false,color: "hx",isHint: true,num: "K",src: "../../static/image/card/13-hx.png",type: "hx"},
					{card: 13,cardvalue: "K",checked: false,color: "ht",isHint: true,num: "K",src: "../../static/image/card/13-ht.png",type: "ht"},
					{card: 12,cardvalue: "Q",checked: false,color: "mh",isHint: true,num: "Q",src: "../../static/image/card/12-mh.png",type: "mh"},
					{card: 11,cardvalue: "J",checked: false,color: "ht",isHint: true,num: "J",src: "../../static/image/card/11-ht.png",type: "ht"},
					{card: "10",cardvalue: "10",checked: false,color: "hx",isHint: true,num: "10",src: "../../static/image/card/10-hx.png",type: "hx"},
				],
				play4paper: [],
				show1: false,
				show2: false,
				show3: false,
				audio: {},
				mp3: '/static/f.mp3',
				showpaper: true,
				sendBtn: false,
				chooseArray: [], //选择的牌
				pushcard: [],
				timer: 5, // 计时器
				timeBtn: false,
				landlordCard: [], //地主牌
				island: false, //是否显示地主牌列表
				landsure: false //是否抢地主
			}
		},
		methods: {
			// 出牌
			showcard() {
				// play(2)
				console.log(requestUrl.startGame)
				var myaudio=new Audio();
				myaudio.src='/static/audio/3.mp3';
				myaudio.play()
			},
			testhit(num) {
				var card = [];
				switch (num) {
					case 0:
						
						break;
					case 1:
						// 单张
						
						break;
					case 2:
						// 对子
						
						break;
					case 3:
						// 三张
						
						break;
					case 4:
						// 三带一
						
						break;
					case 5:
						// 三带二
						
						break;
					case 6:
						// 四带二
					
						break;
					case 7:
						// 四带两对
						
						break;
					case 8:
						// 顺子
						
						break;
					case 9:
						// 连对
						
						break;
					case 10:
						// 飞机
						
						break;
					case 11:
						// 飞机带单
						
						break;
					case 12:
						// 飞机带双
						
						break;
					case 13:
						// 炸弹
						
						break;
					case 14:
						// 王炸
						
						break;
				}
			
			},
		
		checkCard(item, index) {
				// 选择牌
				this.play3paper[index].checked = !this.play3paper[index].checked;
			},
			
			

		},
		onLaunch: function() {
			// 锁定横屏
			plus.screen.lockOrientation('landscape-primary'); //锁定
		}
	}
</script>

<style>
	.play3{
		position:absolute;
		left:50%;
		bottom:0;
		width:100%;
		margin-left:-50%;
		text-align: center;
	}
	.clearfix:after {
		content: "";
		display: block;
		height: 0;
		clear: both;
		visibility: hidden;
	}

	.clearfix {
		*zoom: 1;
	}

	.paperOperate {
		margin-bottom: 10rpx;
		/* max-width:240rpx; */
		margin: 0 auto;
		margin-bottom: 20rpx;
	}

	.nopaper,
	.hit,
	.surePaper {
		font-size: 16rpx;
		float: left;
		padding: 10rpx 20rpx;
		background: #008000;
		border-radius: 10rpx;
		color: #fff;
	}

	.hit {
		/* margin:0  10rpx */
	}


	.noGrad,
	.grabCard {
		width: 90rpx;
		height: 40rpx;
		background: #64b923;
		border-radius: 40rpx;
		color: #fff;
		font-size: 18rpx;
		line-height: 40rpx;
		font-weight: 530;
	}

	.grabCard {
		background: #f59104;
	}

	
	
	
</style>
