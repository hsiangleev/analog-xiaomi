<template>
	<div id="recommend">
		<div class="w">
			<div class="header clearfix">
				<div class="left">为你推荐</div>
				<div class="right">
					<span @click="slideLeft" :class="{disabled: show}">&lt;</span>
					<span @click="slideRight" :class="{disabled: !show}">&gt;</span>
				</div>
			</div>
			<div class="content" @mouseenter="pausePlay" @mouseleave="autoPlay">
				<ul class="clearfix" :style="{left: ulLeft}">
					<li v-for="(val,index) in contentLi">
						<img :src="val.url" alt="">
						<p>{{ val.p1 }}</p>
						<p>{{ val.p2 }}</p>
						<p>{{ val.p3 }}</p>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "recommend",
		data() {
			return {
				contentLi: [
					{
						url: "././src/assets/pms_1505897517.20426731!140x140.jpg",
						p1: "小米笔记本电脑Pro 15 i7 16G",
						p2: "6999元",
						p3: "175人好评",
					},
					{
						url: "././src/assets/pms_1505208893.47475566!140x140.jpg",
						p1: "米动手表青春版",
						p2: "399元",
						p3: "1420人好评",
					},
					{
						url: "././src/assets/pms_1505719040.81692157!140x140.jpg",
						p1: "红米Note 4X 全网通版 3GB内存",
						p2: "999元",
						p3: "899人好评",
					},
					{
						url: "././src/assets/pms_1505401464.03824312!140x140.jpg",
						p1: "小米MIX2 全网通版 6GB内存 黑色陶瓷 64GB",
						p2: "3299元",
						p3: "3887人好评",
					},
					{
						url: "././src/assets/pms_1497524942.16076085!140x140.jpg",
						p1: "小蚁微单相机M1标准变焦套机",
						p2: "2199元",
						p3: "102人好评",
					},
					{
						url: "././src/assets/pms_1499074956.45695759!140x140.jpg",
						p1: "红米4A 移动4G+版 2GB内存 16GB",
						p2: "599元",
						p3: "270人好评",
					},
					{
						url: "././src/assets/pms_1496833357.9528722!140x140.jpg",
						p1: "手机USB micro 数据线",
						p2: "9.9元",
						p3: "2921人好评",
					},
					{
						url: "././src/assets/pms_1504778935.57065093!140x140.jpg",
						p1: "米家运动鞋 男款",
						p2: "199元",
						p3: "116人好评",
					},
					{
						url: "././src/assets/pms_1503969309.57226971!140x140.jpg",
						p1: "小米5X 移动4G+版",
						p2: "1499元",
						p3: "341人好评",
					},
					{
						url: "././src/assets/pms_1487145639.576173!140x140.jpg",
						p1: " 小米Note 2 全球版 6GB内存＋128GB容量",
						p2: "3499元",
						p3: "2796人好评",
					},
				],
				ulLeft: "0%",
				timer: null,
				show: true,
				timer2: null,
				timer3: null,
			}
		},
		methods: {
			slideRight() {
				this.show=false;
				clearInterval(this.timer);
				this.timer=setInterval(()=>{
					if(parseInt(this.ulLeft)<=-100){
						clearInterval(this.timer);
						return;
					}
					this.ulLeft=parseInt(this.ulLeft)-5+"%";
				}, 20)
			},
			slideLeft() {
				this.show=true;;
				clearInterval(this.timer);
				this.timer=setInterval(()=>{
					if(parseInt(this.ulLeft)>=0){
						clearInterval(this.timer);
						return;
					}
					this.ulLeft=parseInt(this.ulLeft)+5+"%";
				}, 20)
			},
			autoPlay() {
				clearInterval(this.timer2);
				clearInterval(this.timer3);
				this.timer2=setInterval(()=>{
					this.slideRight();
				}, 4000);
				this.timer3=setInterval(()=>{
					this.slideLeft();
				}, 6000);
			},
			pausePlay() {
				clearInterval(this.timer2);
				clearInterval(this.timer3);
			}
		},
		mounted() {
			this.autoPlay();
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
	#recommend{
		padding-bottom: 50px;
		width: 100%;
		background-color: #f5f5f5;
		.header{
			width: 100%;
			height: 50px;
			.left{
				font: 500 22px/40px "Microsoft Yahei";
				float: left;
			}
			.right{
				float: right;
				span{
					width: 36px;
					height: 24px;
					display: inline-block;
					border: 1px solid #ccc;
					text-align: center;
					line-height: 24px;
					margin-top: 15px;
					cursor: pointer;
					user-select: none;
					&.disabled{
						color: #ccc;
						cursor: default;
					}
				}
			}
		}
		.content{
			width: 100%;
			height: 370px;
			overflow: hidden;
			position: relative;
			ul{
				width: 210%;
				height: 100%;
				position: absolute;
				left: 0;
				li{
					float: left;
					width: 230px;
					height: 340px;
					background-color: #fff;
					margin-right: 10px;
					text-align: center;
					font-size: 14px;
					@include shadow;
					img{
						width: 160px;
						height: 160px;
						margin-bottom: 20px;
					}
					p{
						margin: 7px 0;
						&:nth-of-type(2){
							color: $redColor;
						}
						&:nth-of-type(3){
							color: #aaa;
						}
					}
				}
			}
		}
	}
</style>