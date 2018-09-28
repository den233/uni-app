<template>
	<view>
		 <form  >
		    <view class="section">
				<input placeholder="这是一个可以自动聚焦的input" focus/>
			</view>
		 </form>
		 <view class="big-modal">
		 	<view class="modal-box">
		 		<view class="modal-title"><text class="text-center">隆力奇会员注册协议</text></view>
		 		<view class="modal-dialog">
		 			<view class="content">
		 
		 				为了明确双方的权利和义务，规范双方业务行为，改善客服服务，本着平等互利的原则，推荐会员（即推荐人以下简称"甲方"）与被推荐会员（即被推荐人以下简称"乙方"）就新会员注册的相关事宜达成本承诺，承诺双方应予遵守。
		 
		 				<view>01、甲方介绍乙方成为隆力奇会员，甲方必须与乙方签定承诺书。</view>
		 
		 				<view>02、乙方在承诺书上点击同意即视为认可该承诺书的内容，属自愿行为。</view>
		 
		 				<view>03、甲方不得代替乙方确认承诺书，一经查实，甲方承担所有责任。</view>
		 
		 				<view>04、甲方不得收取乙方的报单金额和任何费用，告知乙方将钱款直接打入隆力奇指定账户和如何购买产品。</view>
		 
		 				<view>05、订货之日起30天内产品完好包装不影响二次销售的，可办理退货，需扣除相关费用等，并取消经销商资格；超过30天的订货不再办理退货手续（可换货）。</view>
		 
		 				<view>06、甲方没有用诱导、欺骗、宣传暴富等手段骗取乙方成为会员。</view>
		 
		 				<view>07、甲方没有向乙方宣传发展下线和以拉人头式的销售模式。</view>
		 
		 				<view>08、甲方没有向乙方承诺在一定时间内能达到具体多少收入等。</view>
		 
		 				<view>09、甲方未与乙方签定承诺书的，乙方出现任何问题均由甲方负责解决。</view>
		 
		 			</view>
		 		</view>
		 		<view class="footer b-t">
		 			<label> 
					 <checkbox-group @change="checkboxChange">
						<checkbox  value="0" :checked="checked"   /> 我已阅读并同意以上协议
		 			</checkbox-group>
					</label>
					<button @tap="btnTap" class="footer-btn">开始注册</button>
		 		</view>
		 	</view>
		 </view>
	</view>
	
</template>

<script>
	export default {
		data: {
			checked:false
		},
		methods:{
			 btnTap:function(){
				 console.log(this.checked)
			 },
			 checkboxChange:function(e){
				  if(e.detail.value.length>0){
					  this.checked=true
				  }else{
					  this.checked=false
				  }
			 }
		}
	}
</script>

<style>
   .big-modal{
	    position: absolute;
		top: 0%;
		left: 0%;
		background: rgba(0, 0, 0, 0.3);
		width: 100%;
		height: 100%;
		position: fixed;
		z-index: 9999;
		 
   }
    .big-modal .modal-box{
		position: absolute;
		top: 13%;
		left: 4%;
		border-radius: 8px;
		max-width: 92%;
		background-color: #fff;
		overflow-y: auto;
		padding-bottom: 15px;
	} 
	.big-modal .modal-box .modal-title{
		text-align: center;
		margin-top: 5px;
		font-size: 18px;
		padding: 10px 15px;
		background: #fff;
		border-bottom: 1px solid #c8c7cc;
	}
	.big-modal .modal-box .modal-dialog{
		
	}
	.big-modal .modal-box .footer{
		padding: 10px 15px 0 15px;
	}
	.big-modal .modal-box .footer .footer-btn{
		background: #12b3b3;
		width: 100%;
		height: 100%;
		text-align: center;
		color: #fff;
		border-radius: 5px;
		padding: 15px 0;
		font-size: 18px;
		margin-top: 10px;
	}
	.big-modal .modal-box .modal-dialog .content{
		padding: 0 15px 10px 15px;
		max-height: 250px;
		overflow: auto;
		background: #fff;
	}
	.b-t {
		border-top: 1px solid #dddddd;
	}
	 
</style>
