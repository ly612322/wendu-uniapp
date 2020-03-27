<template>
	<view class="content">
		<!--  登录页 -->
		<view class="login">
			<view class="top">
				<view class="top-title">
					文都管联研究院
				</view>
				<view class="top-menu">
					<view class="top-login">
						登录
					</view>
					<view class="top-sign">
						注册
					</view>
				</view>
			</view>
			<view class="main">
				<view class="main-input">
					<input class="input" type="text" placeholder="用户名" placeholder-style="color:#565656; text-align: center;" value="" />
				</view>
				<view class="main-input">
					<input class="input" type="text" placeholder="密码" placeholder-style="color:#565656; text-align: center;" value="" />
				</view>
			</view>
			<view class="main-opt">
				<view class="remember">
					<checkbox-group name="">
						<label>
							<checkbox :value="true" /><text style="color: #ababab;margin-left: 5upx;">记住密码</text>
						</label>
					</checkbox-group>
				</view>
				<view class="forgot">
					忘记密码?
				</view>
			</view>
			<view class="enter">
				<view class="enter-title">
					登录
				</view>
				<text class="enter-icon text-white cuIcon-right"></text>
			</view>
			<view class="login-fac" @click="tryUse">
				<view class="login-fac-title">
					试用一下
				</view>
				<text class="login-fac-icon text-white cuIcon-right"></text>
			</view>

		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {
			tryUse() {
				uni.switchTab({
					url: '/pages/index/index'
				});
			}

		},
	}
</script>

<style>
	@import url("./index.css");
</style>
