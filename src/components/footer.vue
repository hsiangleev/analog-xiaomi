<template>
	<div id="foot">
		<div class="w">
			<div class="top clearfix">
				<div class="icon" :style="icon"></div>
				<div class="text">
					<ul class="clearfix">
						<li v-for="val in navLi">{{ val }}</li>
					</ul>
					<p v-for="val in text">{{ val }}</p>
				</div>
				<div class="oImg">
					<ul class="clearfix">
						<li v-for="val in imgUrl"><img :src="val" alt=""></li>
					</ul>
				</div>
			</div>
			<div class="bott" :style="bottImg"></div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "foot",
		data() {
			return {
				icon: {
					background: 'url("./src/assets/mi-logo.png") top 3px left 4px',
					backgroundColor: "#ff6700",
				},
				bottImg: {
					background: 'url("./src/assets/slogan2016.png")',
					backgroundRepeat: 'no-repeat',
				},
				botImg: "./src/assets/slogan2016.png",
				navLi: ["小米商城","MIUI","米聊","多看书城","小米路由器","视频电话","小米天猫店","小米网盟","小米移动","隐私政策","Select Region"],
				text: ["©mi.com 京ICP证110507号 京ICP备10046444号 京公网安备11010802020134号 京网文[2014]0059-0009号 ","违法和不良信息举报电话：185-0130-1238，本网站所列数据，除特殊说明，所有数据均出自我司实验室测试"],
				imgUrl: ["./src/assets/truste.png","./src/assets/v-logo-2.png","./src/assets/v-logo-1.png","./src/assets/v-logo-3.png"]
			}
		}
	}
</script>

<style lang="scss">
	#foot{
		width: 100%;
		background-color: #fafafa;
		.w{
			position: relative;
			height: 140px;
			.top{
				width: 100%;
				height: 80px;
				padding-top: 20px;
				position: absolute;
				top: 0px;
				left: 0px;
				.icon{
					width: 55px;
					height: 55px;
					float: left;
					cursor: pointer;
				}
				.text{
					float: left;
					font-size: 12px;
					width: 730px;
					height: 55px;
					ul{
						margin: 0px 0px 0px 10px;
						li{
							float: left;
							padding: 0 5px;
							cursor: pointer;
							border-right: 1px solid #888;
							&:last-of-type{
								border: none;
							}
							&:hover{
								color: #ff6700;
							}
						}
					}
					p{
						margin: 5px 0px 0px 15px;
						padding: 0px;
						color: #ccc;
						&:first-of-type{
							color: #888;
						}
					}
				}
				.oImg{
					float: right;
					ul{
						li{
							float: left;
							img{
								width: 83px;
								height: 28px;
							}
						}
					}
				}
			}
			.bott{
				height: 20px;
				width: 270px;
				text-align: center;
				position: absolute;
				left: 0px;
				top: 100px;
				left: 50%;
				margin-left: -135px;
			}
		}
	}
</style>