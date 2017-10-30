<template>
	<div id="myheader">
		<div class="w">
			<!-- 左边导航条 -->
			<div class="header-left">
				<ul class="clearfix">
					<li v-for="(val,index) in headerData"><a href="javascript:;">{{ val }}</a></li>
				</ul>
			</div>
			<!-- 购物车 -->
			<div class="shopCar" @mouseenter="isShow=true" @mouseleave="isShow=false">
				购物车（{{ num }}）
				<transition name="show">
					<div class="car" v-if="isShow">购物车中还没有商品，赶紧选购吧！</div>
				</transition>
				
			</div>
			<!-- 右边导航条 -->
			<div class="header-right">
				<ul class="clearfix">
					<li v-for="(val,index) in headerDataRight"><a href="javascript:;">{{ val }}</a></li>
				</ul>
			</div>
		</div>
			
	</div>
</template>

<script>
	export default{
		name: "myheader",
		data() {
			return {
				headerData: ["小米商城","MIUI","米聊","游戏","多看阅读","云服务","金融","米币","小米商城手机版","问题反馈","Select Region"],
				headerDataRight: ["登录","注册","消息通知"],
				num: 0,
				isShow: false
			}
		},
		methods: {
			show() {
				this.isShow=true;
			},
			hide() {
				this.isShow=false;
			}
		}

	}
</script>


<style lang="scss">

.show-enter-active {
  animation: show-in .3s;
}
.show-leave-active {
  animation: show-out .3s;
}
@keyframes show-in {
  0% {
    height: 0;
  }
  100% {
    height: 100px;
  }
}
@keyframes show-out {
  0% {
    height: 100px;
  }
  100% {
    height: 0px;
  }
}

.clearfix:after{
	content: " ";
	visibility:hidden;
	display:block;
	font-size:0;
	clear:both;
	height:0;
}
.clearfix{
	zoom: 1;
}
$redColor: #ff6700;
@mixin headerUl{
	ul{
		li{
			float: left;
			&:after{
				content: "|";
			}
			&:last-of-type:after{
				content: "";
			}
			a{
				display: inline-block;
				padding: 0 5px;
				&:hover{
					color: #fff;
				}
			}
		}
	}
}
#myheader {
	width: 100%;
	height: 40px;
	line-height: 40px;
	font-size: 12px;
	background-color: #333;
	color: #b0b0b0;
	.header-left{
		float: left;
		@include headerUl;
	}
	.header-right{
		float: right;
		position: relative;
		@include headerUl;
	}
	.shopCar{
		width: 120px;
		height: 40px;
		float: right;
		cursor: pointer;
		margin-left: 10px;
		color: #b0b0b0;
		text-align: center;
		background-color: #424242;
		position: relative;
		&:hover{
			color: $redColor;
			background-color: #fff;
		}
		.car{
			width: 316px;
			height: 100px;
			line-height: 100px;
			box-shadow: 0px 3px 5px #ccc;
			position: absolute;
			top: 40px;
			right: 0;
			display: inline-block;
			color: #333;
			z-index: 5;
			background-color: #fff;
			overflow: hidden;
		}
	}
}

</style>