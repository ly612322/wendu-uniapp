<template>
	<view class="container">
		<!-- <view class="m_nav">
			<ul class="list_group">
				<li class="list_item">MBA</li>
				<li class="list_item">MPA</li>
				<li class="list_item">MTA</li>
				<li class="list_item">MEM</li>
				<li class="list_item">MPAcc</li>
				<li class="list_item">MLis</li>
				<li class="list_item">MAud</li>
			</ul>
		</view>
		<view class="page-section-spacing">
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration"
			 :circular='true'>
				<swiper-item>
					<view class="swiper-item">
						<image style="width: 100%;height: 100%;" mode="aspectFill" src="../../static/image/banner1.png">
						</image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image style="width: 100%;height: 100%;" mode="aspectFill" src="../../static/image/banner2.png"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="sec_image_group">
			<image class="sec_image" src="../../static/image/nav2_1.png" mode=""></image>
			<image class="sec_image" src="../../static/image/nav2_2.png" mode=""></image>
			<image class="sec_image" src="../../static/image/nav2_3.png" mode=""></image>

		</view>
		<view>
			<uni-grid :column="4" :show-border="false" :square="false" style="margin-bottom: 15px;">
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_1.png" mode=""></image>
					<p class="image_name">报考条件</p>
				</uni-grid-item>
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_2.png" mode=""></image>
					<p class="image_name">报考费用</p>
				</uni-grid-item>

				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_3.png" mode=""></image>
					<p class="image_name">院校专业</p>
				</uni-grid-item>
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_4.png" mode=""></image>
					<p class="image_name">报考时间</p>
				</uni-grid-item>
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_5.png" mode=""></image>
					<p class="image_name">报考流程</p>
				</uni-grid-item>
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_6.png" mode=""></image>
					<p class="image_name">报考科目</p>
				</uni-grid-item>
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_7.png" mode=""></image>
					<p class="image_name">备考方案</p>
				</uni-grid-item>
				<uni-grid-item class="grid_item">
					<image class="grid_image" src="../../static/image/nav3_8.png" mode=""></image>
					<p class="image_name">考试时间</p>
				</uni-grid-item>
			</uni-grid>
		</view>
		<view class="main_content">
			<view class="major_content" style="background:url(../../static/image/major_bg.png) no-repeat center center;background-size: cover;">
				<h2 class="major_title">管联类联考可以报的专业</h2>
				<image class="major_main" src="../../static/image/major_img.png" mode=""></image>
			</view>
		</view> -->
		<scroll-view scroll-x class="bg-white nav mynav" scroll-with-animation :scroll-left="scrollLeft">
			<view class="flex text-center">
				<view class="cu-item flex-sub" :class="index==TabCur?'text-blue cur':''" v-for="(item,index) in tabList" :key="index"
				 @tap="tabSelect" :data-id="index">
					{{item}}
				</view>
			</view>
		</scroll-view>
		<view style="margin-top: 80rpx;">
			<swiper class="screen-swiper" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true"
			 :autoplay="true" interval="5000" duration="500" @change="cardSwiper" indicator-color="#8799a3"
			 indicator-active-color="#0081ff">
				<swiper-item v-for="(item,index) in swiperList" :key="index" :class="cardCur==index?'cur':''">
					<view class="swiper-item">
						<image :src="item.url" mode="aspectFill" v-if="item.type=='image'"></image>
						<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="">
			<view class="cu-list grid" :class="['col-' + gridCol,gridBorder?'':'no-border']">
				<view class="cu-item" v-for="(item,index) in cuIconList" :key="index" v-if="index<gridCol*2">
					<view :class="['cuIcon-' + item.cuIcon,'text-' + item.color]">
						<view class="cu-tag badge" v-if="item.badge!=0">
							<block v-if="item.badge!=1">{{item.badge>99?'99+':item.badge}}</block>
						</view>
					</view>
					<text>{{item.name}}</text>
				</view>
			</view>
		</view>
		<view class="cu-card article">
			<view class="cu-item shadow">
				<view class="title">
					<view class="text-cut">测试用小图卡片</view>
				</view>
				<view class="content">
					<image src="https://ossweb-img.qq.com/images/lol/web201310/skin/big10006.jpg" mode="aspectFill"></image>
					<view class="desc">
						<view class="text-content">测试用卡片文字~ 测试用卡片文字~ 测试用卡片文字~ 测试用卡片文字~ </view>
						<view>
							<view class="cu-tag bg-red light sm round">测试标记</view>
							<!-- <view class="cu-tag bg-green light sm round"></view> -->
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="cu-card case" >
			<view class="cu-item shadow">
				<view class="image">
					<image src="https://ossweb-img.qq.com/images/lol/web201310/skin/big10006.jpg" mode="widthFix"></image>
					<view class="cu-tag bg-blue">自定义标记</view>
					<view class="cu-bar bg-shadeBottom"> <text class="text-cut">测试用大图卡片~</text></view>
				</view>
				<view class="cu-list menu-avatar">
					<view class="cu-item">
						<view class="cu-avatar round lg" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big10006.jpg);"></view>
						<view class="content flex-sub">
							<view class="text-grey">测试图片 天使</view>
							<view class="text-gray text-sm flex justify-between">
								十天前
								<view class="text-gray text-sm">
									<text class="cuIcon-attentionfill margin-lr-xs"></text> 10
									<text class="cuIcon-appreciatefill margin-lr-xs"></text> 20
									<text class="cuIcon-messagefill margin-lr-xs"></text> 30
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 	<view class="margin flex">
			<view class="bg-black flex-sub margin-right radius shadow-lg">
				<image src="https://image.weilanwl.com/gif/loading-black.gif" mode="aspectFit" class="gif-black response" style="height:240upx"></image>
			</view>
			<view class="bg-white flex-sub radius shadow-lg">
				<image src="https://image.weilanwl.com/gif/loading-white.gif" mode="aspectFit" class="gif-white response" style="height:240upx"></image>
			</view>
		</view> -->

		<!-- 	<basics v-if="PageCur=='basics'"></basics>
			<components v-if="PageCur=='component'"></components>
			<plugin v-if="PageCur=='plugin'"></plugin> -->
		<!-- 	<view class="cu-bar tabbar bg-white shadow foot">
			<view class="action" @click="NavChange" data-cur="basics">
				<view class='cuIcon-cu-image'>
					<image :src="'/static/tabbar/basics' + [PageCur=='basics'?'_cur':''] + '.png'"></image>
				</view>
				<view :class="PageCur=='basics'?'text-green':'text-gray'">元素</view>
			</view>
			<view class="action" @click="NavChange" data-cur="component">
				<view class='cuIcon-cu-image'>
					<image :src="'/static/tabbar/component' + [PageCur == 'component'?'_cur':''] + '.png'"></image>
				</view>
				<view :class="PageCur=='component'?'text-green':'text-gray'">组件</view>
			</view>
			<view class="action" @click="NavChange" data-cur="plugin">
				<view class='cuIcon-cu-image'>
					<image :src="'/static/tabbar/plugin' + [PageCur == 'plugin'?'_cur':''] + '.png'"></image>
				</view>
				<view :class="PageCur=='plugin'?'text-green':'text-gray'">扩展</view>
			</view>
			<view class="action" @click="NavChange" data-cur="about">
				<view class='cuIcon-cu-image'>
					<image :src="'/static/tabbar/about' + [PageCur == 'about'?'_cur':''] + '.png'"></image>
				</view>
				<view :class="PageCur=='about'?'text-green':'text-gray'">我的</view>
			</view>
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				PageCur: 'basics',
				drawer: false,
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				cardCur: 0,
				swiperList: [{
					id: 0,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
				}, {
					id: 1,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
				}, {
					id: 2,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
				}, {
					id: 3,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg'
				}, {
					id: 4,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big25011.jpg'
				}, {
					id: 5,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big21016.jpg'
				}, {
					id: 6,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big99008.jpg'
				}],
				dotStyle: false,
				towerStart: 0,
				direction: '',
				cuIconList: [{
					cuIcon: 'cardboardfill',
					color: 'red',
					badge: 120,
					name: '报考条件'
				}, {
					cuIcon: 'recordfill',
					color: 'orange',
					badge: 1,
					name: '报考费用'
				}, {
					cuIcon: 'picfill',
					color: 'yellow',
					badge: 0,
					name: '院校专业'
				}, {
					cuIcon: 'noticefill',
					color: 'olive',
					badge: 22,
					name: '报考时间'
				}, {
					cuIcon: 'upstagefill',
					color: 'cyan',
					badge: 0,
					name: '报考流程'
				}, {
					cuIcon: 'clothesfill',
					color: 'blue',
					badge: 0,
					name: '考试科目'
				}, {
					cuIcon: 'discoverfill',
					color: 'purple',
					badge: 0,
					name: '备考方案'
				}, {
					cuIcon: 'questionfill',
					color: 'mauve',
					badge: 0,
					name: '相关帮助'
				}, {
					cuIcon: 'commandfill',
					color: 'purple',
					badge: 0,
					name: '问答'
				}, {
					cuIcon: 'brandfill',
					color: 'mauve',
					badge: 0,
					name: '版权'
				}],
				modalName: null,
				gridCol: 4,
				gridBorder: false,
				tabList: ["精选", "面试", "逻辑", "数学", "写作", "英语"],
				TabCur: 0,
				scrollLeft: 0

			}
		},
		methods: {
			NavChange: function(e) {
				this.PageCur = e.currentTarget.dataset.cur
			},
			DotStyle(e) {
				this.dotStyle = e.detail.value
			},
			// cardSwiper
			cardSwiper(e) {
				this.cardCur = e.detail.current
			},
			tabSelect(e) {
				this.TabCur = e.currentTarget.dataset.id;
				console.log(this.TabCur)
				this.scrollLeft = (e.currentTarget.dataset.id - 1) * 60
			}
		}
	}
</script>

<style>
	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
	}

	.mynav {
		position: fixed;
		top: 0;
		z-index: 999;

	}

	.intro {
		font-size: 14px;
		line-height: 24px;
	}

	.m_nav {
		overflow-x: scroll;
		width: 100%;
		height: 50px;
	}

	.list_group {
		padding: 0;
		width: 120vw;
		overflow-x: scroll;
		float: left;
	}

	.list_item {
		text-align: left;
		float: left;
		list-style: none;
		width: 90rpx;
		font-size: 20px;
		margin: 14px 0 14px 14px;
	}

	.list_item:nth-child(1) {
		margin-left: 10px;
	}

	.list_item:nth-child(5) {
		margin-right: 20px;
	}

	.swiper {
		height: 230px;
	}

	.swiper-item {
		width: 100%;
		height: 100%;
	}

	.swiper_btn_group {
		position: absolute;
		top: 150px;
		left: 20px;
		display: flex;
	}

	.swiper_btn {
		font-size: 10px;
		margin-right: 10rpx;
		background-color: #DD524D !important;
		color: white !important
	}

	.swiper_btn:nth-child(2) {
		background: transparent !important;
		color: #DD524D !important
	}

	.sec_image {
		margin: 15rpx 5rpx 15rpx 15rpx;
		width: 230rpx;
		height: 180rpx;
	}

	.grid_item {
		text-align: center;
		margin-bottom: 10px;

	}

	.grid_image {
		width: 100rpx;
		height: 100rpx;
		margin: 20rpx 40rpx 20rpx 40rpx;

	}

	.image_name {
		font-size: 30rpx;
	}

	.main_content {
		margin-top: 0;
		padding: 2px 8px;
		background-color: #e8e8e8;
	}

	.major_content {
		text-align: center;
		margin-top: 10rpx;
		width: 100%;
		height: 400px;

	}

	.major_image {
		width: 100%;
		height: 80%;

	}

	.major_title {
		font-size: 42rpx;
		font-weight: 400;
		display: inline-block;
		margin-top: 30px;
	}

	.major_main {
		margin-top: 25px;
		width: 60%;
		height: 60%;
	}
</style>
