<template>
	<div id="hotreview">
		<div class="w clearfix">
			<div class="header">
				热评产品
			</div>
			<div class="content" v-for="val in contentArr">
				<img :src="val.url" alt="">
				<p>{{ val.p1 }}</p>
				<p>来自于 {{ val.p2 }} 的评价</p>
				<p>{{ val.p3 }}<span>{{ val.span }}</span></p>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "hotreview",
		data() {
			return {
				contentArr: [
					{
						url: "./src/assets/8949026b-fa9a-4370-989b-5d5e2f149106.jpg",
						p1: "安装简洁方便，信号不错！！！！！",
						p2: "追逆",
						p3: "小米路由器3 | ",
						span: "149元"
					},
					{
						url: "./src/assets/7e051b10-ed56-43df-bd60-3780592a3345.jpg",
						p1: "有了它，妈妈再也不用担心我喝不到健康的水了。呵呵，良心产品，平民价格，对现在的水质起到了很好的改善作...",
						p2: "爱疯911",
						p3: "小米净水器 | ",
						span: "1299元"
					},
					{
						url: "./src/assets/97d80b35-152e-4934-af34-402251458e16.jpg",
						p1: "非常好用，孩子使用防止沉迷于电话影响学习。做工很好，定位基本准确，通话清晰。如果加入时间显示就更完美...",
						p2: "178576259",
						p3: "米兔定位电话 | ",
						span: "169元"
					},
					{
						url: "./src/assets/05972209-0c29-4f2f-9844-09de1093ab02.jpg",
						p1: "样子好可爱，特别是转来转去时很有趣。让它休眠时它就会把头转过去背对着你了，唤醒它又会自动转回来。你叫...",
						p2: "随风",
						p3: "米家小白智能摄像机 | ",
						span: "399元"
					},
				]
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
	#hotreview{
		width: 100%;
		padding-bottom: 30px;
		background-color: #f5f5f5;
		.header{
			padding: 15px 0;
			font: 500 22px/40px "Microsoft Yahei";
		}
		.content{
			width: 283px;
			height: 400px;
			float: left;
			margin-right: 20px;
			background-color: #fff;
			&:last-of-type{
				margin-right: 0px;
			}
			@include shadow;
			img{
				width: 100%;
				height: 220px;
			}
			p{
				margin: 0px;
				font-size: 14px;
				padding: 5px 23px;
				color: #666;
				&:nth-of-type(1){
					margin-top: 20px;
					height: 72px;
					display: block;
				}
				&:nth-of-type(2){
					color: #aaa;
				}
				span{
					color: $redColor;
				}
			}
		}
	}
</style>