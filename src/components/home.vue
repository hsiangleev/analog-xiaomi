<template>
	<div id="home">
		<div class="w" @mouseenter="pausePlay" @mouseleave="autoPlay">
			<!-- 轮播图 -->
			<div class="slideImg">
				<img :src="imgArr[num].url" alt="" >
				<ul>
					<li v-for="(val,index) in imgArr" :class="{current: val.hasCurrent}" @click="changeImg(index)"></li>
				</ul>
				<span @click="subImg">&lt;</span>
				<span @click="addImg">&gt;</span>
			</div>
			<!-- 右边导航 -->
			<div class="left" @mouseleave="hideContent">
				<ul>
					<li v-for="(val,index) in navArr" @mouseenter="showContent(index)">{{ val }}</li>
				</ul>
				<div class="left-content" :style="leftStyle" v-if="isShow">
					<div class="left-content-box" v-for="(val,index) in leftBox[navIndex]">
						<a href="javascript:;" title="">
							<img :src="val.url" alt="">
							<span>{{ val.text }}</span>
						</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "home",
		data() {
			return {
				show: true,
				num: 0,
				imgArr: [
					{
						url: "./src/assets/xmad_1509021435642_OLwaR.jpg",
						hasCurrent: true
					},
					{
						url: "./src/assets/xmad_15058906332794_gQDJX.jpg",
						hasCurrent: false
					},
					{
						url: "./src/assets/xmad_15077714738381_erTKQ.jpg",
						hasCurrent: false
					},
					{
						url: "./src/assets/xmad_15087560386349_Uuhwi.jpg",
						hasCurrent: false
					},
					{
						url: "./src/assets/xmad_15089303073348_sAUOi.jpg",
						hasCurrent: false
					}
				],
				timer: null,
				navArr: ["手机 电话卡","笔记本","电视 盒子","路由器 智能硬件","移动电源 电池 插线板","耳机 音箱","保护套 贴膜","线材 支架 存储卡"],
				leftBox: [
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米5c"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米5c"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
					],
					[
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米5x"
						},
						{
							url: "./src/assets/note3-80-2.png",
							text: "小米Note 3"
						},
						{
							url: "./src/assets/mix2-80.png",
							text: "小米MAX 2"
						},
						{
							url: "./src/assets/xm6_80.png",
							text: "小米6"
						},
					],
				],
				leftStyle: {
					width: "300px"
				},
				navIndex: 0,
				isShow: false
			}
		},
		methods: {
			changeImg(index) {
				this.imgArr[index].hasCurrent=true;
				this.imgArr[this.num].hasCurrent=false;
				this.num=index;
			},
			// 点击左边按钮切换轮播图
			subImg() {
				this.imgArr[this.num].hasCurrent=false;

				if(this.num==0){
					this.num=this.imgArr.length;
				}
				this.imgArr[this.num-1].hasCurrent=true;
				this.num--;
			},
			// 点击右边按钮切换轮播图
			addImg() {
				this.imgArr[this.num].hasCurrent=false;

				if(this.num==this.imgArr.length-1){
					this.num=-1;
				}
				this.imgArr[this.num+1].hasCurrent=true;
				this.num++;
			},
			autoPlay() {
				this.timer=setInterval(()=>{
					this.addImg();
				},2000);
			},
			pausePlay() {
				clearInterval(this.timer);
			},
			showContent(index) {
				this.navIndex=index;
				this.isShow=true;

				var len=this.leftBox[this.navIndex].length;
				if(len<=5){
					this.leftStyle.width="300px";
				}else if(len<=10){
					this.leftStyle.width="600px";
				}else{
					this.leftStyle.width="900px";
				}
			},
			hideContent() {
				this.isShow=false;
			}
		},
		mounted() {
			this.autoPlay();
		}
	}
</script>

<style lang="scss">
	$redColor: #ff6700;
	#home{
		width: 100%;
		.w{
			border: 1px solid #ccc;
			height: 460px;
			position: relative;
			.slideImg{
				width: 100%;
				height: 100%;
				position: absolute;
				left: 0;
				img{
					width: 100%;
					height: 100%;
				}
				ul{
					position: absolute;
					bottom: 10px;
					right: 50px;
					li{
						width: 12px;
						height: 12px;
						float: left;
						margin: 0 5px;
						cursor: pointer;
						border-radius: 50%;
						background-color: #666;
						&:hover,
						&.current{
							background-color: #ccc;
						}
					}
				}
				span{
					display: inline-block;
					position: absolute;
					width: 40px;
					height: 80px;
					color: #fff;
					text-align: center;
					line-height: 80px;
					font-size: 30px;
					top: 50%;
					right: 0px;
					margin-top: -40px;
					cursor: pointer;
					user-select: none;
					&:hover{
						background-color: rgba(0,0,0,0.4);
					}
					&:first-of-type{
						right: none;
						left: 243px;
					}
				}
			}
			.left{
				width: 243px;
				height: 100%;
				position: absolute;
				left: 0;
				background-color: rgba(0,0,0,0.4);
				ul{
					padding-top: 20px;
					li{
						color: #fff;
						padding: 15px 20px;
						cursor: pointer;
						font-size: 14px;
						&:after{
							content: ">";
							float: right;
						}
						&:hover{
							background-color: $redColor;
						}
					}
				}
				.left-content{
					height: 100%;
					background-color: #fff;
					position: absolute;
					left: 100%;
					top: 0px;
					.left-content-box{
						width: 250px;
						height: 50px;
						line-height: 30px;
						margin: 20px;
						position: relative;
						display: inline-block;
						a{
							display: inline-block;
							width: 100%;
							color: #333;
							span{
								position: absolute;
								top: 5px;
								left: 70px;
							}
							&:hover{
								color: $redColor;
							}
						}
					}
				}
			}
		}
	}
</style>