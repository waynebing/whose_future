<template>
	<view style="background: url('../../static/icon/123.jpg') no-repeat contain;">
		<view class="cu-bar search select_area" :style="[{top:CustomBar + 'px'}]">
			<view class="search-form round select_search">
				<text class="cuIcon-search"></text>
				<input class="search_box" type="text" placeholder="搜索" confirm-type="search" @tap="searchIcon"></input>
			</view>
		</view>
		<view class="swipper_container">
			<swiper class="screen-swiper swiper_screen" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true"
			 :autoplay="true" interval="5000" duration="500">
				<swiper-item v-for="(item,index) in swiperList" :key="index">
					<image :src="item.url" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="school_list">
			
			<view class="cu-card article school_card" :class="isCard?'no-card':''" v-for="(item,index) in schoolList" :key="index">
				<view class="cu-item shadow school_item" >
					<view class="title"><view class="text-cut" style="background: url('../../static/icon/sclectschool/sch-title.png') no-repeat 48%;">成都计算机职业技术学院</view></view>
					<view class="content">
						<image src="../../static/icon/index/img-school1.png"
						 mode="aspectFill" style="border-radius: 16rpx;"></image>
						<view class="desc">
							<view class="text-content hot_major">热门专业</view>
							<view class="text-tags">
								<view class='cu-tag line-gray round sm'>{{item.tags1}}</view>
								<view class='cu-tag line-gray round sm'>{{item.tags2}}</view>
								<view class='cu-tag line-gray round sm'>{{item.tags3}}</view>
							</view>
							<view class="text-look">
								<image src="../../static/icon/index/icon-number.png"></image>
								<text class="look_num">{{item.num}}人</text>
							</view>
						</view>
					</view>
				</view>
			</view>
			
			
		</view>
	</view>
</template>
<script>
export default {
  data(){
	  return{
		  CustomBar: this.CustomBar,
		  swiperList: [{
				id: 0,
				type: 'image',
				url: '../../static/icon/sclectschool/sch-banner.png'
			}, {
				id: 1,
				type: 'image',
				url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
			}, {
				id: 2,
				type: 'image',
				url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
			}],
			schoolList:[
			{
				id:0,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				tags4:'',
				num:500
			},
			{
				id:1,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				num:1200
			},
			{
				id:2,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				num:300
			},
			{
				id:3,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				num:270
			},
			{
				id:4,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				num:900
			},
			{
				id:5,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				num:1201
			},
			{
				id:6,
				tags1:'信息工程',
				tags2:'网络工程',
				tags3:'计算机与科学技术',
				num:217
			}],
			dotStyle: false,
			isCard:false
	  }
  },
  mounted () {
    
  },
  components: {
    
  },
  computed: {
   
  },
  methods: {
    searchIcon(e) {
		uni.navigateTo({
			url:'../pagesB/Search/search'
		});
	},
	DotStyle(e) {
		this.dotStyle = e.detail.value
	},
  }
}
</script>

<style>
 page{
 }
/* .select_area{
	margin-top:24upx ;
} */
.select_search{
	height: 80upx !important;
}
.search_box{
	padding-left: 14upx;
}
.cuIcon-search:before{
	color:#474747 !important;
	font-size: 36px;
	font-weight: bold;
}
.swipper_container{
	margin-top: 24upx;
	width: 700upx;
	height: 276upx;
	margin: 24rpx auto;
}
.swipper_container .swiper_screen{
	border-radius: 16upx;
}
.swipper_container swiper-item{
	border-radius: 16upx;
}
/* .school_card{
	background-image: url(data:image/jpeg;base64,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);
	background-repeat: no-repeat;
	background-size:cover;
} */
.cu-tag{
	color: #D9D7D7;
}
.school_list{
	width: 100%;
	min-height: 20vh;
	margin-top: 130upx;
	padding-bottom: 50upx;
}
.school_card{
	width: 730upx;
	margin: 0 auto;
}
.school_item{
	margin: 0 !important;
	margin-top: 22upx !important;
	margin-left: 26upx !important;
	margin-right: 26upx !important;
}
.hot_major{
	height: 40upx !important;
}
.text-cut{
	text-align: center;
}
.text-tags{
	height: 120upx;
	line-height: 120upx;
	overflow: hidden;
	text-overflow: ellipsis;
}
.text-tags view{
	color: #575757;
	height: 36upx !important;
	padding: 0upx 20upx !important;
	height: 50upx !important;
	font-size: 28px !important;
}
.text-look image{
	width: 36upx;
	height: 30upx;
	vertical-align: middle;
}
.look_num{
	display: inline-block;
	padding-left:5upx ;
	color: #787F86;
	font-size: 24px;
}
</style>
