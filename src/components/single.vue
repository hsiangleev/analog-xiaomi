<template>
	<div id="single">
		<div class="w">
			<div class="header clearfix">
				<div class="left">小米明星单品</div>
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
		name: "single",
		data() {
			return {
				contentLi: [
					{
						url: "././src/assets/xmad_1496643954435_EcHtv.png",
						p1: "小米Max 2",
						p2: "大屏大电量，享多重好礼",
						p3: "1399元起",
					},
					{
						url: "././src/assets/xmad_1489401341687_vUojl.png",
						p1: "红米Note 4X",
						p2: "4100mAh超长续航，多彩金属",
						p3: "999元起",
					},
					{
						url: "././src/assets/xmad_14966625747867_qcTyh.png",
						p1: "红米4X",
						p2: "4100mAh超长续航，8 核处理器",
						p3: "699元起",
					},
					{
						url: "././src/assets/pms_1503909150.67293503!220x220.png",
						p1: "小米电视4A 43英寸 标准版",
						p2: "全高清HDR 四核高性能处理器",
						p3: "1899元",
					},
					{
						url: "././src/assets/725a37e3-78b7-4298-8098-c40097bf179d.png",
						p1: "小米笔记本",
						p2: "更轻更薄，像杂志一样随身携带",
						p3: "3599元起",
					},
					{
						url: "././src/assets/xmad_15078617619273_gRwzn.png",
						p1: "米家智能摄像机云台版",
						p2: "红外夜视，720P分辨率",
						p3: "199元",
					},
					{
						url: "././src/assets/6ef55907-bbed-49be-a2bb-be0821b5f7b8.png",
						p1: "小米手环 2",
						p2: "OLED 显示屏幕，升级计步算法",
						p3: "149元",
					},
					{
						url: "././src/assets/T1ZYC_BjWv1RXrhCrK.jpg",
						p1: "米家压力IH电饭煲",
						p2: "智能烹饪，压力IH加热技术",
						p3: "999元",
					},
					{
						url: "././src/assets/xmad_14972549116226_tZpod.png",
						p1: "米家空气净化器Pro",
						p2: "OLED显示屏幕，激光颗粒物传感器",
						p3: "1499元",
					},
					{
						url: "././src/assets/de35852a-1be5-4ef5-846f-dcdd2efcfea6.png",
						p1: "小米路由器3",
						p2: "更快更强，不止四天线",
						p3: "119元",
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
	#single{
		margin-top: 15px;
		margin-bottom: 50px;
		width: 100%;
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
			height: 340px;
			overflow: hidden;
			position: relative;
			ul{
				width: 210%;
				position: absolute;
				left: 0;
				li{
					float: left;
					width: 234px;
					height: 340px;
					background-color: rgba(160,160,160,0.1);
					margin-right: 7px;
					text-align: center;
					font-size: 14px;
					border-top: 1px solid #cc0;
					&:nth-of-type(2),
					&:nth-of-type(7){
						border-top: 1px solid #c0c;
					}
					&:nth-of-type(3),
					&:nth-of-type(8){
						border-top: 1px solid #0cc;
					}
					&:nth-of-type(4),
					&:nth-of-type(9){
						border-top: 1px solid #0c0;
					}
					&:nth-of-type(5),
					&:nth-of-type(10){
						border-top: 1px solid #00c;
					}
					img{
						width: 160px;
						height: 160px;
						margin-bottom: 20px;
					}
					p{
						margin: 7px 0;
						&:nth-of-type(2){
							color: #aaa;
						}
						&:nth-of-type(3){
							color: $redColor;
						}
					}
				}
			}
		}
	}
</style>