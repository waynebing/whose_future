<template>
	<view>
		<view class="analysis_back">
			<view class="user_info">
				<view>
					<view class="user_name">李婉婉</view>
					<view class="user_introduce"><text class="user_sex">女</text><text class="user_phone">18980411988</text></view>
				</view>
				<view class="cu-avatar xl round margin-left" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big99008.jpg);"></view>
			</view>
			<view class="analysis_character">
				<view class="character_title">森女甜系活泼女</view>
				<view class="character_type">
					<view class="character_content" v-for="(item,index) in 5" :key="index">
						<image src="../../../static/icon/index/index-icon3.png" mode=""></image>
						<view>读书</view>
					</view>
				</view>
			</view>
		</view>
		<view class="analysis_result">
			<view class="result_title">
				测评结果
			</view>
			
			<!-- 适合的专业开始 -->
			<view class="result_box">
				<text class="result_sub_title">适合的专业</text>
			</view>
			<view class="result_word">
				<text>信息工程、软件工程、网络工程、软件工程、</text>
			</view>
			<!-- 适合的专业结束 -->
			<!-- 适合的学校开始 -->
			<view class="result_box">
				<text class="result_sub_title">适合的学校</text>
			</view>
			<view class="guess_like">
				<view class="flex" style="justify-content: flex-start">
					<view class="flex-sub margin-xs radius guess_like_box">
						<view>
							<image class="guess_like_school" src="../../../static/icon/index/img-school1.png" mode=""></image>
							<view class="guess_like_name">
								<image src="../../../static/icon/index/icon-hot.png" mode=""></image>
								<text>成都机械职业技术学院</text>
							</view>
							<view class="guess_like_num">
								<image src="../../../static/icon/index/icon-number.png" mode=""></image>
								<text>1000人</text>
							</view>
						</view>
					</view>
					<view class="flex-sub margin-xs radius guess_like_box">
						<view>
							<image class="guess_like_school" src="../../../static/icon/index/img-school1.png" mode=""></image>
							<view class="guess_like_name">
								<image src="../../../static/icon/index/icon-hot.png" mode=""></image>
								<text>成都机械职业技术学院</text>
							</view>
							<view class="guess_like_num">
								<image src="../../../static/icon/index/icon-number.png" mode=""></image>
								<text>1000人</text>
							</view>
						</view>
					</view>
				</view>
				<!-- 换一批 -->
				<view class="change_batch">
					<image src="../../../static/icon/index/icon-change.png"></image>
				</view>
			</view>
			<!-- 适合的学校结束 -->
			<!-- 就业前景开始 -->
			<view class="result_box">
				<text class="result_sub_title">就业前景</text>
			</view>
			<view class="result_word">
				<text>即员工职位等级由低级到高级的晋升，如由经</text>
				<text>由助理工程师晋升到工程师的职位</text>
				<text>纵向的职业发展主要强调的是员工职位承担责任由小到大，如由经</text>
				<text>员工职位承担内容的挑战性由小到大</text>
			</view>
			<!-- 就业前景结束 -->
		</view>
	</view>
</template>

<script>
	
</script>

<style>
	page{
		background-color: #24324F;
	}
	.analysis_back{
		width: 100%;
		height: 460upx;
		background-color: #8F000B;
	}
	.user_info{
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
		padding-top: 60upx;
	}
	.user_name{
		color: #FFFFFF;
		font-size: 40px;
		font-weight: bold;
	}
	.user_introduce{
		margin-top: 16upx;
	}
	.user_sex{
		font-size: 28px;
		color: #FFD6D8;
	}
	.user_phone{
		font-size: 28px;
		color: #FFD6D8;
		display: inline-block;
		margin-left: 15upx;
	}
	.analysis_character{
		width: 700upx;
		height: 264upx;
		background-color: #FFFFFF;
		border-radius:16upx;
		margin:48upx auto;
	}
	.character_title{
		padding-top: 44upx;
		text-align: center;
		color: #1C2023;
		font-size: 32px;
	}
	.character_type{
		display: flex;
		justify-content: space-around;
		align-items: center;
		flex-direction: row;
		margin-top: 46upx;
	}
	.character_content{
		display: inline-block;
	}
	.character_content image{
		width: 64upx;
		height: 64upx;
	}
	.character_content view{
		color: #787F86;
		font-size: 20px;
		text-align: center;
	}
	.analysis_result{
		width: 700upx;
		background-color: #fff;
		margin: 70upx auto;
		border-radius:16upx;
		padding-bottom: 50upx;
	}
	.result_title{
		text-align: center;
		padding-top: 28upx;
		color: #1C2023;
		font-size: 32px;
	}
	.result_box{
		text-align: center;
		margin-top: 32upx;
	}
	.result_sub_title{
		color: #fff;
		background-color: #2A2A2A;
		font-size: 28px;
		display: inline-block;
	}
	.result_word{
		width: 616upx;
		margin: 18upx auto;
		text-align: center;
	}
	.result_word text{
		color: #333333;
		font-size: 28px;
		display: inline-block;
		min-height: 38upx;
		border-bottom: 1rpx dotted #86AECA;
		line-height: 50upx;
		padding-top: 14upx;

	}
	.guess_like{
		margin-top: 40upx;
	}
	.guess_like_box{
		background-color: #fff;
		width: 254rpx;
		height: 352rpx;
		margin-left: 5rpx;
		margin-right: 5rpx;
	}
	.guess_like_school{
		width: 370upx;
		height: 248upx;
	}
	.guess_like_name image{
		width: 22upx;
		height: 22upx;
	}
	.guess_like_name text{
		color: #333;
		padding-left: 10upx;
		line-height: 28upx;
	}
	.guess_like_num{
		text-align: left;
		padding-left: 0;
	}
	.guess_like_num image{
		width: 26upx;
		height: 18upx;
	}
	.guess_like_num text{
		color: #787F86;
		font-size: 24rpx;
		padding-left: 10upx;
	}
	/* 换一批 */
	.change_batch{
		text-align: center;
	}
	.change_batch image{
		width: 140upx;
		height: 40upx;
	}
</style>
