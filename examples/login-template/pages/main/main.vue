<template>
    <view class="container">
		<view>
			<swiper  :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item v-for="item in array" :key="item">
					 <image style="width: 100%; height: 400px; background-color: #eeeeee;" :mode="item.mode" :src="src" @error="imageError"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="icons grid">
			<view class="row">
				<view class="col text-cebter" @tap="addMember">
					<image   mode="aspectFill" class="home-menu-icon" src="/static/img/home-entry-member.png"></image>
					<view>会员注册</view>	  
				</view>
				<view class="col text-cebter">
				<image class="home-menu-icon" src="/static/img/home-entry-order.png"></image>
				<view>新增订单</view>	  
				</view>
				<view class="col text-cebter">
				<image class="home-menu-icon" src="/static/img/home-entry-goods.png"></image>
				<view>商品分类</view>	  
				</view>
				<view class="col text-cebter">
				<image class="home-menu-icon" src="/static/img/home-entry-money.png"></image>
				<view>充值钱包</view>	  
				</view>
				<view class="col text-cebter">
				<image class="home-menu-icon" src="/static/img/home-entry-bonus.png"></image>
				<view>奖金提现</view>	  
				</view>
			</view>
			 
		</view> 
    </view>
</template>

<script>
    import {
        mapState
    } from 'vuex'

    export default {
		data: {
			array: [{
					mode: 'aspectFill',
					text: 'scaleToFill：不保持纵横比缩放图片，使图片完全适应'
				}, {
					mode: 'aspectFill',
					text: 'aspectFit：保持纵横比缩放图片，使图片的长边能完全显示出来'
				}, {
					mode: 'aspectFill',
					text: 'aspectFill：保持纵横比缩放图片，只保证图片的短边能完全显示出来'
				} ],
            src: '/static/img/home-banner1.jpg',	
         
			indicatorDots: true,
			autoplay: false,
			interval: 5000,
			duration: 1000
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
			},
			addMember:function(){
				uni.navigateTo({
					url: '../addmember/addmember'
				});
			}
		},
        computed: mapState(['forcedLogin', 'hasLogin', 'userName']),
        onLoad() {
            if (!this.hasLogin) {
                uni.showModal({
                    title: '未登录',
                    content: '您未登录，需要登录后才能继续',
                    /**
                     * 如果需要强制登录，不显示取消按钮
                     */
                    showCancel: !this.forcedLogin,
                    success: (res) => {
                        if (res.confirm) {
							/**
							 * 如果需要强制登录，使用reLaunch方式
							 */
                            if (this.forcedLogin) {
                                uni.reLaunch({
                                    url: '../login/login'
                                });
                            } else {
                                uni.navigateTo({
                                    url: '../login/login'
                                });
                            }
                        }
                    }
                });
            }
        }
    }
</script>

<style>
    .hello {
        display: flex;
        flex: 1;
        flex-direction: column;
    }

    .title {
        color: #8f8f94;
        margin-top: 50px;
    }

    .ul {
        font-size: 30px;
        color: #8f8f94;
        margin-top: 50px;
    }

    .ul>view {
        line-height: 50px;
    }
	.home-menu-icon{
		width:60px;
		height:60px;
	}
	
</style>
