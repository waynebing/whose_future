<template>
	<view>
		<view class="cu-bar search select_area" :style="[{top:CustomBar + 'px'}]">
			<view class="search-form round select_search">
				<input class="search_input" type="text" confirm-type="search" @input="searchIcon"></input>
				<text class="cuIcon-search search_icon"></text>
			</view>
			<view class="selected_tag">
				<view class="tag_item" v-for="(item,index) in selectedItem" :key="index">
					<text class="tag_name">{{item.name}}</text>
					<text class="cuIcon-close close_icon" @tap="clearItem(item)"></text>
				</view>
			</view>
		</view>
		
		<view class="VerticalBox">
			<scroll-view scroll-y class="nav text-center VerticalMain">
				<view class="cu-item" :class="index==TabCur?'text-white cur':''" v-for="(item,index) in tabList" :key="index" @tap="tabSelect"
				 :data-id="index">
					<text class="tab_item">{{item.name}}</text>
				</view>
			</scroll-view>
			<view  v-if="TabCur==0" class="bg-grey padding  text-center search_content">
				<view class="search_banner">
					<image src="../../../static/icon/index/img-like4.png" mode=""></image>
				</view>
				<view class="guess_like">
					<view class="flex" style="justify-content: space-around;">
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
				</view>
			</view>
			<view v-if="TabCur==1" class="bg-grey padding  text-center search_content">
				<view class="school_scale">
					<view>校园类型</view>
					<view class="flex flex-wrap align-center campus_type justify-start">
						<button class="cu-btn round lg" v-for="(item,index) in campusList" @tap="campusType(item)" :class="{'cur':item.size===size}" :key="index">{{item.name}}</button>
						<!-- <button class="cu-btn round lg" @tap="campusType(2)" :class="{'cur':campus==2}">民办</button> -->
					</view>
					<view class="row_2">人员规模</view>
					<view class="flex flex-wrap align-center staff_size justify-start">
						<button class="cu-btn round lg" v-for="(item,index) in staffList" @tap="staffSize(item)" :class="{'cur':item.id===type}" :key="index">{{item.name}}</button>
					</view>
				</view>
			</view>
			<view v-if="TabCur==2" class="bg-grey padding  text-center search_content">
				<view class="school_scale">
					<view>国家级实验室</view>
					<view class="flex flex-wrap align-center staff_size justify-start">
						<button class="cu-btn round lg" v-for="(item,index) in labList" @tap="laboratory(item)" :class="{'cur':item.id===lab}" :key="index">{{item.name}}</button>
					</view>
					<view>示范工地</view>
					<view class="flex flex-wrap align-center staff_size justify-start">
						<button class="cu-btn round lg" v-for="(item,index) in demonList" @tap="demonstrationSites(item)" :class="{'cur':item.id==demon}" :key="index">{{item.name}}</button>
					</view>
				</view>
			</view>
			<view v-if="TabCur==3" class="bg-grey padding  text-center search_content">
				<view class="school_scale">
					<view>计算机方向</view>
					<view class="flex flex-wrap align-center campus_type justify-start">
						<button class="cu-btn round lg" v-for="(item,index) in professionalList" @tap="orientation(item)" :class="{'cur':item.id==profession}" :key="index">{{item.name}}</button>
					</view>
					<!-- <view>机械制造方向</view>
					<view class="flex flex-wrap align-center campus_type justify-start">
						<button class="cu-btn round lg" @tap="machinery(1)" :class="{'cur':machine==1}">挖掘机</button>
						<button class="cu-btn round lg" @tap="machinery(2)" :class="{'cur':machine==2}">电焊</button>
						<button class="cu-btn round lg" @tap="machinery(3)" :class="{'cur':machine==3}">汽修</button>
					</view> -->
				</view>
			</view>
			<view v-if="TabCur==4" class="bg-grey padding  text-center search_content">
			</view>
			<view v-if="TabCur==5" class="bg-grey padding margin text-center search_content">
				关注度
			</view>
		</view>
		
	</view>
</template>

<script>
	const STAFF = 1 ,
		  CAMPUS = 0,
		  LAB = 2,
		  DEMON = 3,
		  PROFRSSION = 4;
	export default {
		data() {
			return {
				CustomBar: this.CustomBar,
				load: true,
				TabCur: 0,
				scrollLeft: 0,
				tabList:[{
					id:0,
					name:'猜你喜欢'
				},
				{
					id:1,
					name:'学校规模'
				},
				{
					id:2,
					name:'学校设施'
				},
				{
					id:3,
					name:'专业选择'
				},
				{
					id:4,
					name:'学校荣誉'
				},
				{
					id:5,
					name:'关注度'
				}],
				campusList:[
					{ name: '公办',size:1,type:CAMPUS },
					{ name: '民办',size:2,type:CAMPUS },
				],
				staffList:[
					{name:'<500',id:1,type:STAFF},
					{name:'500<人数<1000',id:2,type:STAFF},
					{name:'1000<人数<2000',id:3,type:STAFF},
					{name:'2000<人数<5000',id:4,type:STAFF},
					{name:'5000<人数<1万',id:5,type:STAFF},
					{name:'1万<人数<2万',id:6,type:STAFF}
				],
				labList:[
					{name:'成都瑞华实验室',id:1,type:LAB},
					{name:'成都爱力普实验室',id:2,type:LAB},
					{name:'成都方凯仂实验室',id:3,type:LAB}
				],
				demonList:[
					{name:'省级示范工地',id:1,type:DEMON},
					{name:'市级示范工地',id:2,type:DEMON},
					{name:'县级示范工地',id:3,type:DEMON}
				],
				professionalList:[
					{name:'网络工程',id:1,type:PROFRSSION},
					{name:'计算机科学与技术',id:2,type:PROFRSSION},
					{name:'信息工程',id:3,type:PROFRSSION},
					{name:'软件工程',id:4,type:PROFRSSION},
					{name:'电子自动化',id:5,type:PROFRSSION}
				],
				selectedItem:[],
				sites:0,
				less:'<',
				size:null,
				type:null,
				lab:null,
				demon:null,
				profession:null
			}
		},
		onLoad() {
			uni.showLoading({
				title: '加载中...',
				mask: true
			});
		},
		onReady() {
			uni.hideLoading()
		},
		components: {

		},
		methods: {
			searchIcon(e) {
				console.log('当前输入:', e.detail.value);
			},
			tabSelect(e) {
				this.TabCur = e.currentTarget.dataset.id;
				this.scrollLeft = (e.currentTarget.dataset.id - 1) * 60
			},
			campusType(item){
				let index = -1;
				for(let ls of this.selectedItem){
					if(this.campusList.includes(ls)){
						// this.selectedItem.splice(this.selectedItem.indexOf(ls),1);
						index=this.selectedItem.indexOf(ls);
						this.selectedItem[index]=item;
						break;
					}
				}
				this.size=item.size;
				index===-1 && this.selectedItem.push(item);
				// this.selectedItem.push(item);
				console.log(this.selectedItem);
				// if(item.size===PUBLIC){
				// 	index=this.selectedItem.indexOf(this.campusList[1]);
				// }else{
				// 	index=this.selectedItem.indexOf(this.campusList[0]);
				// }
				// index>-1 && 
				// if (!item.selected) {//选中状态点击
				// 	item.selected = true//变为不选中状态
				// 	this.selectedItem.push(item);
				// 	console.log('当前数组:',this.selectedItem);
				// } else if (item.selected) {//不选中状态点击
				// 	item.selected = false
				// 	const i = this.selectedItem.indexOf(item)//找到当前点击项
				// 	this.selectedItem.splice(i, 1)//移除一个不选中项
				// };
			},
			staffSize(item){
				let index=-1;
				for(let ls of this.selectedItem){
					if(this.staffList.includes(ls)){
						index=this.selectedItem.indexOf(ls);
						this.selectedItem[index]=item;
						break;
						// this.selectedItem.splice(this.selectedItem.indexOf(ls),1);
					}
				}
				this.type=item.id;
				index===-1 && this.selectedItem.push(item);
				// index!== -1 || this.selectedItem.push(item);
			},
			laboratory(item){
				let index=-1;
				for(let ls of this.selectedItem){
					if(this.labList.includes(ls)){
						index=this.selectedItem.indexOf(ls);
						this.selectedItem[index]=item;
						break;
						// this.selectedItem.splice(this.selectedItem.indexOf(ls),1);
					}
				}
				this.lab=item.id;
				index===-1 && this.selectedItem.push(item);
				// index!== -1 || this.selectedItem.push(item);
			},
			demonstrationSites(item){
				let index=-1;
				for(let ls of this.selectedItem){
					if(this.demonList.includes(ls)){
						index=this.selectedItem.indexOf(ls);
						this.selectedItem[index]=item;
						break;
						// this.selectedItem.splice(this.selectedItem.indexOf(ls),1);
					}
				}
				this.demon=item.id;
				index===-1 && this.selectedItem.push(item);
			},
			orientation(item){
				let index=-1;
				for(let ls of this.selectedItem){
					if(this.professionalList.includes(ls)){
						index=this.selectedItem.indexOf(ls);
						this.selectedItem[index]=item;
						break;
						// this.selectedItem.splice(this.selectedItem.indexOf(ls),1);
					}
				}
				this.profession=item.id;
				index===-1 && this.selectedItem.push(item);
			},
			machinery(e){
				this.machine = e;
			},
			clearItem(item){
				const i = this.selectedItem.indexOf(item);//找到当前点击项
				this.selectedItem.splice(i,1);
				if(item.type===0){
					this.size=null;
				}else if(item.type === 1){
					this.type=null;
				}else if(item.type === 2){
					this.lab = null;
				}else if(item.type === 3){
					this.demon = null;
				}else if(item.type === 4){
					this.profession = null;
				}
			}
		}
	}
</script>

<style>
	page {
		background-color: #24324F;
	}
	.cu-bar{
		display: block;
		margin-top: 30upx !important;
	}
	.select_area{
		/* display: flex;
		flex-direction: column; */
	}
	.search_icon {
		margin: 0 2em 0 0.8em !important;
	}
	.cuIcon-search:before{
		color: #474747;
		font-size: 36px;
		font-weight: bold;
	}
	.close_icon{
		margin: 0 0.1em 0 0.1em !important;
	}
	.search_input {
		padding-left: 50upx;
	}
	.selected_tag{
		width: 700upx;
		margin: 20upx auto;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		align-items: center;
		min-height: 90upx;
		flex-wrap: wrap;
	}
	.tag_item{
		height: 32upx;
		/* width: 20%; */
		background-color: #fff;
		border-radius:26upx;
		margin-left: 10upx;
	}
	.tag_name{
		font-size: 24px;
		padding-left: 15upx;
	}
	.VerticalMain {
		flex: 1;
		width: 140upx;
		height: 100vh;
	}
	.VerticalBox {
		display: flex;
	}
	.VerticalBox .cu-item{
		display: block;
		margin: 0 4rpx !important;
		padding: 0 4rpx !important;
		color: #bbc0c9 !important;
	}
	.VerticalBox .cu-item.cur{
		border-bottom: 0 !important;
		border-left: 4px solid #A2494D;
		color: #fff !important;
	}
	.search_content{
		flex: 5;
		background-color: #24324F;
	}
	.tab_item{
		display: inline-block;
		margin-left: 10upx;
	}
	.search_banner{
		width: 100%;
		height: 232upx;
		overflow: hidden;
	}
	.search_banner image{
		width: 100%;
		height: 232upx;
	}
	.guess_like_box{
		background-color: #fff;
		width: 254rpx;
		height: 352rpx;
		margin-left: 5rpx;
		margin-right: 5rpx;
	}
	.guess_like_school{
		width: 300upx;
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
		padding-left: 18upx;
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
	/* 学校规模 */
	.school_scale{
		color: #fff;
		text-align: left;
		padding-left: 60upx;
	}
	.campus_type{
		margin-top: 24upx;
	}
	.campus_type button{
		margin-right: 16upx;
		color: #787F86;
		margin-bottom: 16upx;
	}
	.campus_type button.cur{
		background-color: #850410;
		color: #fff;
	}
	/* 人员规模 */
	.row_2{
		margin-top: 60upx;
	}
	.staff_size{
		margin-top: 24upx;
		flex-direction: column;
		align-items: flex-start;
	}
	.staff_size button{
		margin-right: 16upx;
		color: #787F86;
		margin-bottom: 16upx;
	}
	.staff_size button.cur{
		background-color: #850410;
		color: #fff;
	}
</style>
