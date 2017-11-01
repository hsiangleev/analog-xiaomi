<template>
	<div id="mycontent">
		<div class="w">
			<div class="header">
				内容
			</div>
			<div class="content">
				<ul class="clearfix">
					<li v-for="(val,index) in conArr" @mouseenter="val.span=true" @mouseleave="val.span=false">
						<h4>{{ val.title }}</h4>
						<ul class="clearfix" :style="{left: val.left, width: val.width}">
							<li v-for="value in val.arr">
								<p>{{ value.p1 }}</p>
								<p>{{ value.p2 }}</p>
								<p>{{ value.p3 }}</p>
								<img :src="value.url" alt="">
							</li>
						</ul>
						<span v-show="val.span" @click="slideRight(index)">&lt;</span>
						<span v-show="val.span" @click="slideLeft(index)">&gt;</span>
						<ol>
							<li v-for="(v,classIndex) in val.arr" :class="{current: v.hasClass}" @click="changeClass(index,classIndex)"></li>
						</ol>
					</li>
				</ul>
						
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "mycontent",
		data() {
			return {
				timer: null,
				conArr: [
					{
						title: "图书",
						left: "0px",
						width: "301%",
						isrun: false,
						oldIndex: 0,
						span: false,
						arr: [
							{
								p1: "哈利·波特与被诅咒的孩子",
								p2: "“哈利·波特”第八个故事中文版震撼来袭！特别彩排版剧本！ ",
								p3: "29.37元",
								url: "./src/assets/5e5da924-84e3-4959-9e25-5891cdf30757.png",
								hasClass: true
							},
							{
								p1: "好吗好的",
								p2: "畅销作家大冰2016年新书！讲给你听，好吗好的！ ",
								p3: "17.99元",
								url: "./src/assets/61e1385e-54de-48f3-8717-5e4f4b1cdd14.png",
								hasClass: false
							},
							{
								p1: " ",
								p2: "海量好书，享受精品阅读时光漂亮的中文排版，千万读者选择！ ",
								p3: "前往多看阅读",
								url: "./src/assets/more-duokan.jpg",
								hasClass: false
							},
						]

					},
					{
						title: "MIUI 主题",
						left: "0px",
						width: "301%",
						isrun: false,
						oldIndex: 0,
						span: false,
						arr: [
							{
								p1: "剑网3",
								p2: "剑网3定制主题 免费下载 ",
								p3: "免费",
								url: "./src/assets/xmad_15078047291113_SunKC.png",
								hasClass: true
							},
							{
								p1: "初音未来",
								p2: "超可爱的miku主题来啦~ ",
								p3: "6米币",
								url: "./src/assets/xmad_15078048061917_BPXjH.png",
								hasClass: false
							},
							{
								p1: "几何",
								p2: "最新官方主题，带你感受极简视觉冲击~ ",
								p3: "免费",
								url: "./src/assets/xmad_14982103643442_KCZrH.jpg",
								hasClass: false
							},
							{
								p1: " ",
								p2: "众多个性主题、百变锁屏与自由桌面 ",
								p3: "前往MIUI主题市场",
								url: "./src/assets/more-miui.jpg",
								hasClass: false
							},
						]
					},
					{
						title: "游戏",
						left: "0px",
						width: "301%",
						isrun: false,
						oldIndex: 0,
						span: false,
						arr: [
							{
								p1: "小米枪战",
								p2: "只拼枪法不拼枪！！ ",
								p3: "免费",
								url: "./src/assets/xmad_15094191317724_FNyjV.png",
								hasClass: true
							},
							{
								p1: "米柚手游模拟器",
								p2: "在电脑上玩遍小米所有手游 ",
								p3: "免费",
								url: "./src/assets/T1czW_BXCv1R4cSCrK.png",
								hasClass: false
							},
							{
								p1: "剑侠世界",
								p2: "一生不容错过的浪漫武侠！！ ",
								p3: "免费",
								url: "./src/assets/695c909b-f541-4575-bace-d08b6465025b.jpg",
								hasClass: false
							},
							{
								p1: " ",
								p2: "免费下载海量的手机游戏,天天都有现金福利赠送 ",
								p3: "前往小米游戏商店",
								url: "./src/assets/more-game.jpg",
								hasClass: false
							},
						]
					},
					{
						title: "应用",
						left: "0px",
						width: "301%",
						isrun: false,
						oldIndex: 0,
						span: false,
						arr: [
							{
								p1: "2017金米奖",
								p2: "最优秀的应用和游戏 ",
								p3: "29.37元",
								url: "./src/assets/3332da7d-4056-4694-9548-c83b7b3af7d3.png",
								hasClass: true
							},
							{
								p1: "Forest",
								p2: "帮助您专心于生活中每个重要时刻 ",
								p3: "免费",
								url: "./src/assets/T1TkKvBCKv1R4cSCrK.png",
								hasClass: false
							},
							{
								p1: " ",
								p2: "帮助小米手机和其他安卓手机用户,发现好用的安卓应用 ",
								p3: "小米应用商店",
								url: "./src/assets/more-app.jpg",
								hasClass: false
							},
						]
					},
				]
			}
		},
		methods: {
			slideLeft(index) {
				// this.conArr[index].isrun：当前动画是否在执行，若当前动画在执行，则再次点击无效（针对快速双击bug）
				if(!this.conArr[index].isrun){
					this.conArr[index].isrun=true;
					// 动画执行的目标点
					var target=parseInt(this.conArr[index].left)-100;
					if(target<=-this.conArr[index].arr.length*100){
						// 动画结束
						this.conArr[index].isrun=false;
						return;
					}
					clearInterval(this.timer);
					this.timer=setInterval(()=>{
						var current=parseInt(this.conArr[index].left);
						if(current>target){
							this.conArr[index].left=current-5+"%";
						}else{
							clearInterval(this.timer);
							// 当前动画结束
							this.conArr[index].isrun=false;
						}
					},20);



					// 切换class
					var i=this.conArr[index].oldIndex;
					this.conArr[index].arr[i+1].hasClass=true;
					this.conArr[index].arr[i].hasClass=false;
					this.conArr[index].oldIndex=i+1;
				}
			},
			slideRight(index) {
				if(!this.conArr[index].isrun){
					this.conArr[index].isrun=true;
					var target=parseInt(this.conArr[index].left)+100;
					if(target>0){
						this.conArr[index].isrun=false;
						return;
					}
					clearInterval(this.timer);
					this.timer=setInterval(()=>{
						var current=parseInt(this.conArr[index].left);
						if(current<target){
							this.conArr[index].left=current+5+"%";
						}else{
							clearInterval(this.timer);
							// 当前动画结束
							this.conArr[index].isrun=false;
						}
					},20);



					// 切换class
					var i=this.conArr[index].oldIndex;
					this.conArr[index].arr[i-1].hasClass=true;
					this.conArr[index].arr[i].hasClass=false;
					this.conArr[index].oldIndex=i-1;
				}	
			},
			changeClass(index,classIndex) {
				var target=-100*classIndex;
				clearInterval(this.timer);
				this.timer=setInterval(()=>{
					// 动画开始执行
					this.conArr[index].isrun=true;
					var current=parseInt(this.conArr[index].left);
					if(current<target){
						this.conArr[index].left=current+5+"%";
					}else if(current>target){
						this.conArr[index].left=current-5+"%";
					}else{
						// 动画执行完成
						this.conArr[index].isrun=false;
						clearInterval(this.timer);
					}
				},20);

				// 切换class
				this.conArr[index].arr[classIndex].hasClass=true;
				this.conArr[index].arr[this.conArr[index].oldIndex].hasClass=false;
				this.conArr[index].oldIndex=classIndex;
			},
		},
		mounted() {
			// 根据图书的个数初始化ul长度
			this.conArr.forEach(function (val,index){
				val.width=val.arr.length*100+1+"%";
			},this)
		}
		
	}
</script>

<style lang="scss">
	// 背景显示
	@mixin shadow{
		&:hover{
			box-shadow: 0 15px 30px rgba(0,0,0,0.1);
			transform: translate3d(0,-2px,0);
		}
	}
	// 为每个盒子定制一个颜色
	@mixin current($num,$color){
		&:nth-of-type(#{$num}){
			border-top: 1px solid $color;
			h4{
				color: $color;
			}
			ol{
				li{
					&:hover,
					&.current{
						background-color: $color;
					}
				}
			}
			ul{
				li:last-of-type p:nth-of-type(3){
					border: 1px solid $color;
					display: inline-block;
					padding: 5px 15px;
					color: $color;
					cursor: pointer;
					&:hover{
						background-color: $color;
						color: #fff;
					}
				}
			}
		}
	} 

	#mycontent{
		width: 100%;
		padding-bottom: 50px;
		background-color: #f5f5f5;
		.header{
			width: 100%;
			height: 40px;
			font: 500 22px/40px "Microsoft Yahei";
		}
		.content{
			width: 100%;
			position: relative;
			&>ul{
				&>li{
					float: left;
					width: 280px;
					height: 420px;
					background-color: #fff;
					margin-right: 23px;
					text-align: center;
					position: relative;
					overflow: hidden;
					@include shadow;
					h4{
						margin: 40px 0 0 0;
					}
					@include current(1,#6f9);
					@include current(2,#69f);
					@include current(3,#ff6);
					@include current(4,#f69);
					&:nth-of-type(4){
						margin-right: 0;
					}
					ul{
						width: 301%;
						height: 350px;
						position: absolute;
						bottom: 0;
						left: 0px;
						li{
							float: left;
							width: 280px;
							text-align: center;
							p{
								padding: 0 10px;
								font-size: 20px;
								&:nth-of-type(2){
									color: #aaa;
									font-size: 12px;
									padding: 0 30px;
								}
								&:nth-of-type(3){
									color: #333;
									font-size: 12px;
								}
							}
							// 由前面定制
							// &:last-of-type p:nth-of-type(3){
							// 	border: 1px solid #f69;
							// 	display: inline-block;
							// 	padding: 5px 15px;
							// 	color: #f69;
							// 	cursor: pointer;
							// 	&:hover{
							// 		background-color: #f69;
							// 		color: #fff;
							// 	}
							// }
							&:last-of-type img{
								display: inline-block;
								margin-top: 20px;
							}
						}
					}
					span{
						width: 20px;
						height: 48px;
						line-height: 48px;
						text-align: center;
						background-color: #ccc;
						position: absolute;
						top: 50%;
						margin-top: -24px;
						color: #fff;
						cursor: pointer;
						&:first-of-type{
							left: 0;
						}
						&:last-of-type{
							right: 0;
						}
					}
					ol{
						padding: 0;
						margin: 0;
						list-style: none;
						position: absolute;
						bottom: 30px;
						left: 50%;
						margin-left: -39px;
						li{
							float: left;
							width: 10px;
							height: 10px;
							margin: 0 8px;
							background-color: #aaa;
							border-radius: 50%;
						}
					}
				}
			}
			
		}
	}
</style>