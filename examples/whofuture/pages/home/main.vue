<template>
    <view class="index">
        <view class="index_banner">
         <image src="../../static/icon/index/index_banner.png"></image>
        </view>
        <view class="index_function">
            <view class="function_top">
                <span>成都</span>
                <span>
					【公告】成都高校信息早知道…dadssadsad
                </span>
            </view>
            <!-- 功能键区开始 -->
            <view class="function_btn">
				<view @tap="gotoAnalysis">
					<image src="../../static/icon/index/index-icon2.png" mode=""></image>
					<view class="function_btn_name">综合分析</view>
				</view>
			</view>
            <!-- 功能键区结束 -->
           
        </view>
         <!-- 热门高校 -->
        <view class="index_popular">
            <view class="like_title">
                <image src="../../static/icon/index/img-title1.png"></image>
            </view>
            <view class="popular_row">
                <view class="popular_box">
                    <view class="like_img">
                        <image src="../../static/icon/index/img-school1.png"></image>
                    </view>
                     <view class="like_content">
                        <span><image src="../../static/icon/index/icon-hot.png"></image></span>
                        成都机械职业技术学院
                    </view>
                    <view class="like_thumbs">
                        <span>
                            <image src="../../static/icon/index/icon-number.png"></image>
                            1000+人
                        </span>
                        <span>
                            <image src="../../static/icon/index/icon-vedio.png"></image>
                            <image src="../../static/icon/index/icon-certification.png"></image>
                            <image src="../../static/icon/index/icon-dot.png"></image>
                        </span>
                    </view>
                </view>
                 <view class="popular_box">
                    <view class="like_img">
                        <image src="../../static/icon/index/img-school2.png"></image>
                    </view>
                     <view class="like_content">
                        <span><image src="../../static/icon/index/icon-hot.png"></image></span>
                        成都机械职业技术学院
                    </view>
                    <view class="like_thumbs">
                        <span>
                            <image src="../../static/icon/index/icon-number.png"></image>
                            1000+人
                        </span>
                        <span>
                            <image src="../../static/icon/index/icon-vedio.png"></image>
                            <image src="../../static/icon/index/icon-certification.png"></image>
                            <image src="../../static/icon/index/icon-dot.png"></image>
                        </span>
                    </view>
                </view>
                
            </view>
            <!-- 换一批 -->
            <view class="change_batch">
                <image src="../../static/icon/index/icon-change.png"></image>
            </view>
        </view>
        <!-- 猜你喜欢 -->
        <view class="index_like">
            <view class="like_title">
                <image src="../../static/icon/index/img-title2.png"></image>
            </view>
            <view class="like_container">
               <view class="like_show">测试</view>
            </view>
        </view>
    </view>
</template>

<script>
// 组件引用

export default {
  data () {
    return {
    }
  },
  components: {
    
  },
  methods: {
     gotoAnalysis(){
		 uni.navigateTo({
		 	url:'../pagesA/Analysis/main'
		 });
	 }
  }
}
</script>

<style>
page{
    background-color: #24324F;
}
.index_banner{
    width: 100%;
    height: 100%;
}
.index_banner image{
	width: 100%;
	height:450upx;
}
.index_function{
	background-color: #6E2626;
	border-radius:24upx;
	width:718upx;
	height:515upx;
	margin: 16upx auto;
}
.function_top {
	width: 100%;
	height: 40upx;
	display: flex;
	flex-direction: row;
	justify-content: space-between;
	align-items: center;
	padding-top: 40upx;
}
.function_top span{
	 color: #fff;
	display: inline-block;
	font-family: "STFangsong";
}
.function_top span:nth-of-type(1){
	padding-left: 22upx;
}
.function_top span:nth-of-type(2){
	padding-right: 0upx;
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap; 
	width: 75%;
}
.function_btn{
	border: 0upx;
	margin-top: 50upx;
	padding-left: 10upx;
}
.function_btn view image{
	width: 90upx;
	height: 90upx;
}
.function_btn .function_btn_name{
	color: #D39393;
}
.index_popular{
	width: 100%;
	height: 600upx;
	margin-top: 40upx;
}
.like_title{
	text-align: center;
}
.like_title image{
	width:558upx;
	height:68upx;
}
.popular_row{
	display: flex;
	justify-content:  space-around;
	align-items: center;
	margin-top: 36upx;
}
.popular_box{
	width: 47%;
	height: 470upx;
	background-color: #fff;
	text-align: center;
}
.popular_box:nth-of-type(2){
	margin-left: -20upx;
}
.like_content{
	color: #1C2023 !important;
	font-size: 28upx;
	text-align: center;
	font-family: "STFangsong";
                    
}
.like_content span image{
	width:28upx;
	height:28upx;
}
.like_thumbs{
	display: flex;
	flex-direction: row;
	justify-content: space-around;
	align-items: center;
	margin-top: 18upx;
}
.like_thumbs span{
	font-size: 28upx;
	color: #212528;
}
.like_thumbs span image{
	width:28upx;
	height:28upx;
}
.like_img image{
	width: 100%;
	height: 340upx;
}
.change_batch{
	text-align: center;
	margin-top: 34upx;
}
.change_batch image{
	width: 140upx;
	height: 40upx;
}
.index_like{
	width: 100%;
	height: 600upx;
	margin-top: 125upx;
}
.like_title{
	text-align: center;
}
.like_title image{
	width:558upx;
	height:68upx;
}
.like_container{
	margin-top: 50upx;
}
.like_show .like_box{
	text-align: center;
	background-color: #A33744;
	width: 47%;
	margin: 10upx 10upx;
}
.like_show .like_box:nth-of-type(2){
	background-color: #fff !important;
}
.like_show .like_box .like_img image{
	width: 100%;
	height: 340upx;
}
.like_content{
	color: #fff;
	font-size: 28upx;
	text-align: center;
	font-family: "STFangsong";
}
.like_thumbs{
	text-align: right;
}
</style>
