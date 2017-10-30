<template>
	<div id="componcon">
		<div class="w">
			<div class="header clearfix">
				<div class="left">{{ msg }}</div>
				<div class="right">
					<ul class="clearfix">
						<li v-for="(val,index) in liArr" :class="{current: val.hasClass}" @mouseenter="changeImg(index)">{{ val.text }}</li>
					</ul>
				</div>
			</div>
			<div class="content clearfix">
				<div class="left">
					<img :src="leftUrl" alt="">
				</div>
				<div class="right">
					<div class="right-content" v-for="val in contentArr[oldIndex]">
						<span>{{ val.title }}</span>
						<img :src="val.url" alt="">
						<p>{{ val.p1 }}</p>
						<p>{{ val.p2 }}</p>
						<p>{{ val.p3 }}</p>
					</div>
					<div class="last-content">
						<div class="last-content-box" v-for="val in lastArr">
							<p>{{ val.p1 }}</p>
							<p>{{ val.p2 }}</p>
							<img :src="val.url" alt="">
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "componcon",
		data() {
			return {
				leftUrl: "./src/assets/d78fc81d-8713-43fe-8387-17f31b4b0745.jpg",
				msg: "家电",
				liArr: [
					{
						text: "热门",
						hasClass: true
					},
					{
						text: "电视影音",
						hasClass: false
					},
					{
						text: "电脑",
						hasClass: false
					},
					{
						text: "家居",
						hasClass: false
					}
				],
				oldIndex: 0,
				contentArr: [
					[
						{
							title: "享9折",
							url: "././src/assets/pms_1500287084.72131750!220x220.jpg",
							p1: "小米电视4A 32",
							p2: "64位四核处理器／1GB+4GB大内存",
							p3: "999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1503909218.70932288!220x220.png",
							p1: "小米电视4A 49英寸 标准版",
							p2: "2GB+8GB 大储存／全高清HDR",
							p3: "1999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1505106710.28498495!220x220.jpg",
							p1: "小米笔记本Pro 15.6英寸 ",
							p2: "全金属强化机身/FHD全贴合屏幕",
							p3: "5599元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1499138177.54329452!220x220.jpg",
							p1: "小米笔记本Air 13.3 i7处理器",
							p2: "Intel酷睿i7处理器，8GB内存+256GB",
							p3: "5999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1465366178.11466342!220x220.jpg",
							p1: "米家恒温电水壶",
							p2: "水温智能控制，304 不锈钢内胆",
							p3: "199元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1508120469.3053874!220x220.jpg",
							p1: "智米全直流变频空调",
							p2: "一级能效，强劲冷暖",
							p3: "4399元"
						},
						{
							title: "享9折",
							url: "././src/assets/T1hMK_BjEv1RXrhCrK!220x220.jpg",
							p1: "小米净水器（厨下式）",
							p2: "大流量直出纯净水，健康家庭必备",
							p3: "1999元"
						},
					],
					[
						{
							title: "享9折",
							url: "././src/assets/pms_1503909300.25797209!220x220.png",
							p1: "小米电视4A 55 标准版",
							p2: "4K高清HDR / 真四核64位高性能处理器",
							p3: "2599元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1495074010.05677255!220x220.jpg",
							p1: "小米电视4 55英寸",
							p2: "4.9mm极超薄机身／4K高清HDR",
							p3: "3999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1495073969.01063180!220x220.jpg",
							p1: "小米电视4 49英寸",
							p2: "4.9mm 极超薄机身／无边框式设计",
							p3: "3299元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1490077569.08131612!220x220.png",
							p1: "小米电视4A 65 标准版",
							p2: "4K超高清屏／真四核64位高性能处理器",
							p3: "4999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1490778418.99894062!220x220.png",
							p1: "小米电视4A 65 标准版",
							p2: "4K超高清屏／真四核64位高性能处理器",
							p3: "5499元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1495074053.84174465!220x220.jpg",
							p1: "小米电视4 65英寸",
							p2: "无边框式设计 / 3GB+32GB超大内存",
							p3: "8999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1479190789.95594557!220x220.jpg",
							p1: "小米盒子3s",
							p2: "4K HDR 人工智能机顶盒",
							p3: "329元"
						},
					],
					[
						{
							title: "享9折",
							url: "././src/assets/pms_1500287084.72131750!220x220.jpg",
							p1: "小米电视4A 32",
							p2: "64位四核处理器／1GB+4GB大内存",
							p3: "999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1503909218.70932288!220x220.png",
							p1: "小米电视4A 49英寸 标准版",
							p2: "2GB+8GB 大储存／全高清HDR",
							p3: "1999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1505106710.28498495!220x220.jpg",
							p1: "小米笔记本Pro 15.6英寸 ",
							p2: "全金属强化机身/FHD全贴合屏幕",
							p3: "5599元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1499138177.54329452!220x220.jpg",
							p1: "小米笔记本Air 13.3 i7处理器",
							p2: "Intel酷睿i7处理器，8GB内存+256GB",
							p3: "5999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1465366178.11466342!220x220.jpg",
							p1: "米家恒温电水壶",
							p2: "水温智能控制，304 不锈钢内胆",
							p3: "199元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1508120469.3053874!220x220.jpg",
							p1: "智米全直流变频空调",
							p2: "一级能效，强劲冷暖",
							p3: "4399元"
						},
						{
							title: "享9折",
							url: "././src/assets/T1hMK_BjEv1RXrhCrK!220x220.jpg",
							p1: "小米净水器（厨下式）",
							p2: "大流量直出纯净水，健康家庭必备",
							p3: "1999元"
						},
					],
					[
						{
							title: "享9折",
							url: "././src/assets/pms_1503909300.25797209!220x220.png",
							p1: "小米电视4A 55 标准版",
							p2: "4K高清HDR / 真四核64位高性能处理器",
							p3: "2599元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1495074010.05677255!220x220.jpg",
							p1: "小米电视4 55英寸",
							p2: "4.9mm极超薄机身／4K高清HDR",
							p3: "3999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1495073969.01063180!220x220.jpg",
							p1: "小米电视4 49英寸",
							p2: "4.9mm 极超薄机身／无边框式设计",
							p3: "3299元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1490077569.08131612!220x220.png",
							p1: "小米电视4A 65 标准版",
							p2: "4K超高清屏／真四核64位高性能处理器",
							p3: "4999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1490778418.99894062!220x220.png",
							p1: "小米电视4A 65 标准版",
							p2: "4K超高清屏／真四核64位高性能处理器",
							p3: "5499元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1495074053.84174465!220x220.jpg",
							p1: "小米电视4 65英寸",
							p2: "无边框式设计 / 3GB+32GB超大内存",
							p3: "8999元"
						},
						{
							title: "享9折",
							url: "././src/assets/pms_1479190789.95594557!220x220.jpg",
							p1: "小米盒子3s",
							p2: "4K HDR 人工智能机顶盒",
							p3: "329元"
						},
					]
				],
				lastArr: [
					{
						p1: "小白摄像机",
						p2: "399元",
						url: "./src/assets/pms_1468806372.46368911!220x220.jpg",
					},
					{
						p1: "浏览更多",
						p2: "热门",
						url: "./src/assets/ico.png",
					}
				]
			}
		},
		methods: {
			changeImg(index) {
				this.liArr[index].hasClass=true;
				this.liArr[this.oldIndex].hasClass=false;
				this.oldIndex=index;
			}
		}
	}
</script>

<style lang="scss">
	
	$redColor: #ff6700;
	@mixin shadow{
		&:hover{
			box-shadow: 0 15px 30px rgba(0,0,0,0.1);
			transform: translate3d(0,-2px,0);
		}
	}
	#componcon{
		width: 100%;
		padding-top: 30px;
		background-color: #f5f5f5;
		.left{
			float: left;
			font: 500 22px/40px "Microsoft Yahei";
		}
		.right{
			float: right;
			ul{
				li{
					float: left;
					margin: 0 10px;
					padding: 0 0 5px 0;
					cursor: pointer;
					&:hover,
					&.current{
						color: $redColor;
						border-bottom: 2px solid $redColor;
					}
				}
			}
		}
		.content{
			width: 100%;
			height: 615px;
			.left{
				width: 234px;
				height: 615px;
				@include shadow;
			}
			.right{
				float: left;
				height: 615px;
				width: 960px;
				.right-content{
					width: 226px;
					height: 300px;
					float: left;
					margin-left: 13px;
					margin-bottom: 14px;
					background-color: #fff;
					@include shadow;
					text-align: center;
					font-size: 14px;
					position: relative;
					span{
						position: absolute;
						top: 0;
						left: 50%;
						display: block;
						padding: 0 10px;
						margin-left: -30px;
						background-color: #e53935;
						color: #fff;
					}
					img{
						margin-top: 15px;
						width: 150px;
						height: 150px;
					}
					p{
						margin: 8px 0;
						&:nth-of-type(2){
							font-size: 12px;
							color: #aaa;
						}
						&:nth-of-type(3){
							color: $redColor;
						}
					}
				}
				.last-content{
					float: left;
					width: 226px;
					.last-content-box{
						width: 100%;
						height: 143px;
						float: left;
						margin-left: 13px;
						margin-bottom: 14px;
						background-color: #fff;
						@include shadow;
						font-size: 14px;
						position: relative;
						img{
							width: 80px;
							height: 80px;
							position: absolute;
							right: 10px;
							top: 50%;
							margin-top: -55px;
						}
						p{
							margin-left: 20px;
							margin-top: 30px;
							&:nth-of-type(2){
								margin-top: 10px;
								color: $redColor;
							}
						}
					}
				}
			}
		}
	}
</style>