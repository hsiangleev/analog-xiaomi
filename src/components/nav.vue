<template>
	<div id="mynav">
		<div class="w clearfix">
			<div class="icon" :style="icon"></div>
			<div class="nav" @mouseleave="show=false">
				<ul class="clearfix" @mouseenter="show=true">
					<li v-for="(val,index) in navUl">
						<a href="javascript:;" @mouseenter="showSlide(index)">{{ val }}</a>
					</li>
				</ul>
				<transition name="fade">
					<div class="slide" v-if="show">
						<div class="slide-box" v-for="(val,index) in slideBox[currentIndex]">
							<span>{{ val.title }}</span>
							<img :src="val.url" alt="">
							<p>{{ val.type }}</p>
							<p>{{ val.price }}</p>
						</div>
					</div>
				</transition>
			</div>
			<div class="search " :class="{changeBorderColor: isShow}">
				<input type="text" @focus="searchShow" @blur="searchHide">
				<span v-show="!isShow">小米Max 2</span>
				<span v-show="!isShow">小米MIX 2 现货</span>
				<button :class="{changeBorderColor: isShow}">√</button>
				<div class="list" :class="{changeBorderColor: isShow}" v-show="isShow">
					<ul>
						<li v-for="(val,index) in list">
							<p>{{ val.type }}</p>
							<p>约有{{ val.num }}件</p>
						</li>
					</ul>
				</div>
			</div>

		</div>
			
			
	</div>
</template>

<script>
	export default{
		name: "mynav",
		data() {
			return {
				icon: {
					background: 'url("./src/assets/mi-logo.png") top 3px left 4px',
					backgroundColor: "#ff6700",
				},
				navUl: ["小米手机","红米","笔记本","电视","盒子","新品","路由器","智能硬件","服务","社区"],
				isShow: false,
				list: [
					{
						type: "小米6",
						num: 7
					},
					{
						type: "红米Node 4X",
						num: 8
					},
					{
						type: "小米MAX",
						num: 1
					},
					{
						type: "小米6",
						num: 7
					},
					{
						type: "红米Node 4X",
						num: 8
					},
					{
						type: "小米MAX",
						num: 1
					},
					{
						type: "小米6",
						num: 7
					},
					{
						type: "红米Node 4X",
						num: 8
					},
					{
						type: "小米MAX",
						num: 1
					},
				],
				slideBox: [
					[
						{
							title: "新品",
							url: "./src/assets/mix2320-220.png",
							type: "小米MIX2",
							price: "3299起"
						},
						{
							title: "新品",
							url: "./src/assets/note2320x220.png",
							type: "小米Node 3",
							price: "2499起"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/xm6-320.png",
							type: "小米6",
							price: "2499起"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/max2_toubu.png",
							type: "小米MAX2",
							price: "1399起"
						},
						{
							title: "新品",
							url: "./src/assets/5x-2!160x110.jpg",
							type: "小米5X",
							price: "1499起"
						},
						{
							title: "新品",
							url: "./src/assets/xiaomiNOTE2-320-220!160x110.jpg",
							type: "小米Node 2",
							price: "2799起"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/320-220-1.png",
							type: "红米5A",
							price: "599元"
						},
						{
							title: "新品",
							url: "./src/assets/3205a.png",
							type: "红米Note 5A 标准版",
							price: "699元"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/320-220!160x110.jpg",
							type: "红米Note 5A 高配版",
							price: "899元"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/hmn4xtb!160x110.jpg",
							type: "红米Note 4X",
							price: "999元"
						},
						{
							title: "新品",
							url: "./src/assets/hm4x!160x110.jpg",
							type: "红米4X",
							price: "699元"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/mix2320-220.png",
							type: "小米MIX2",
							price: "3299起"
						},
						{
							title: "新品",
							url: "./src/assets/note2320x220.png",
							type: "小米Node 3",
							price: "2499起"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/xm6-320.png",
							type: "小米6",
							price: "2499起"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/max2_toubu.png",
							type: "小米MAX2",
							price: "1399起"
						},
						{
							title: "新品",
							url: "./src/assets/5x-2!160x110.jpg",
							type: "小米5X",
							price: "1499起"
						},
						{
							title: "新品",
							url: "./src/assets/xiaomiNOTE2-320-220!160x110.jpg",
							type: "小米Node 2",
							price: "2799起"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/320-220-1.png",
							type: "红米5A",
							price: "599元"
						},
						{
							title: "新品",
							url: "./src/assets/3205a.png",
							type: "红米Note 5A 标准版",
							price: "699元"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/320-220!160x110.jpg",
							type: "红米Note 5A 高配版",
							price: "899元"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/hmn4xtb!160x110.jpg",
							type: "红米Note 4X",
							price: "999元"
						},
						{
							title: "新品",
							url: "./src/assets/hm4x!160x110.jpg",
							type: "红米4X",
							price: "699元"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/mix2320-220.png",
							type: "小米MIX2",
							price: "3299起"
						},
						{
							title: "新品",
							url: "./src/assets/note2320x220.png",
							type: "小米Node 3",
							price: "2499起"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/xm6-320.png",
							type: "小米6",
							price: "2499起"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/max2_toubu.png",
							type: "小米MAX2",
							price: "1399起"
						},
						{
							title: "新品",
							url: "./src/assets/5x-2!160x110.jpg",
							type: "小米5X",
							price: "1499起"
						},
						{
							title: "新品",
							url: "./src/assets/xiaomiNOTE2-320-220!160x110.jpg",
							type: "小米Node 2",
							price: "2799起"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/320-220-1.png",
							type: "红米5A",
							price: "599元"
						},
						{
							title: "新品",
							url: "./src/assets/3205a.png",
							type: "红米Note 5A 标准版",
							price: "699元"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/320-220!160x110.jpg",
							type: "红米Note 5A 高配版",
							price: "899元"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/hmn4xtb!160x110.jpg",
							type: "红米Note 4X",
							price: "999元"
						},
						{
							title: "新品",
							url: "./src/assets/hm4x!160x110.jpg",
							type: "红米4X",
							price: "699元"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/mix2320-220.png",
							type: "小米MIX2",
							price: "3299起"
						},
						{
							title: "新品",
							url: "./src/assets/note2320x220.png",
							type: "小米Node 3",
							price: "2499起"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/xm6-320.png",
							type: "小米6",
							price: "2499起"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/max2_toubu.png",
							type: "小米MAX2",
							price: "1399起"
						},
						{
							title: "新品",
							url: "./src/assets/5x-2!160x110.jpg",
							type: "小米5X",
							price: "1499起"
						},
						{
							title: "新品",
							url: "./src/assets/xiaomiNOTE2-320-220!160x110.jpg",
							type: "小米Node 2",
							price: "2799起"
						},
					],
					[
						{
							title: "新品",
							url: "./src/assets/320-220-1.png",
							type: "红米5A",
							price: "599元"
						},
						{
							title: "新品",
							url: "./src/assets/3205a.png",
							type: "红米Note 5A 标准版",
							price: "699元"
						},
						{
							title: "陶瓷版现货",
							url: "./src/assets/320-220!160x110.jpg",
							type: "红米Note 5A 高配版",
							price: "899元"
						},
						{
							title: "享多重优惠",
							url: "./src/assets/hmn4xtb!160x110.jpg",
							type: "红米Note 4X",
							price: "999元"
						},
						{
							title: "新品",
							url: "./src/assets/hm4x!160x110.jpg",
							type: "红米4X",
							price: "699元"
						},
					],
				],
				currentIndex: 0,
				addZero: "none",
				show: false
			}
		},
		methods: {
			searchShow() {
				this.isShow=true;
			},
			searchHide() {
				this.isShow=false;
			},
			showSlide(index) {
				if(index<8){
					this.addZero="1px solid #ccc";
					this.currentIndex=index;
				}
					
			},
			hideSlide(){
				this.addZero="none";
			}
		}
	}
</script>

<style lang="scss">

	.fade-enter-active {
	  animation: fade-in .3s;
	}
	.fade-leave-active {
	  animation: fade-out .3s;
	}
	@keyframes fade-in {
	  0% {
	    height: 0;
	  }
	  100% {
	    height: 220px;
	  }
	}
	@keyframes fade-out {
	  0% {
	    height: 220px;
	  }
	  100% {
	    height: 0px;
	  }
	}



	$redColor: #ff6700;
	@mixin changeBorderColor{
		&.changeBorderColor{
			border: 1px solid $redColor;
		}
	}
	#mynav{
		width: 100%;
		height: 100px;
		position: relative;
		.icon{
			width: 55px;
			height: 55px;
			cursor: pointer;
			margin-top: 25px;
			float: left;
		}
		.nav{
			float: left;
			margin-top: 15px;
			margin-left: 188px;
			ul{
				li{
					float: left;
					a{
						display: inline-block;
						margin: 26px 10px 38px 10px;
						color: #333;
						&:hover{
							color: $redColor;
						}
					}
				}
			}
			.slide{
				position: absolute;
				top: 100px;
				left: 0px;
				background-color: #fff;
				width: 100%;
				height: 220px;
				font-size: 12px;
				padding: 0 80px;
				box-sizing: border-box;
				border-top: 1px solid #ccc;
				box-shadow: 0 2px 3px #ccc;
				overflow: hidden;
				z-index: 2;
				.slide-box{
					width: 190px;
					height: 100%;
					float: left;
					text-align: center;
					position: relative;
					cursor: pointer;
					span{
						display: inline-block;
						height: 20px;
						line-height: 20px;
						padding: 0 8px;
						border: 1px solid $redColor;
					}
					img{
						width: 80%;
						margin-top: 20px;
					}
					p{
						margin: 5px 0;
						&:last-of-type{
							color: $redColor;
						}
					}
					&:after{
						content: "";
						height: 120px;
						width: 2px;
						display: inline-block;
						background-color: #ddd;
						position: absolute;
						right: 0px;
						top: 40px;
					}
					&:last-of-type:after{
						width: 0px;
					}
				}
			}
		}
		.search{
			float: right;
			width: 296px;
			height: 50px;
			border: 1px solid #ccc;
			margin-top: 25px;
			position: relative;
			@include changeBorderColor;
			input{
				height: 46px;
				width: 230px;
				border: none;
				outline: none;
				position: absolute;
				left: 15px;
			}
			span{
				height: 20px;
				display: inline-block;
				background-color: #ddd;
				color: #666;
				position: absolute;
				top: 15px;
				left: 65px;
				font-size: 12px;
				cursor: pointer;
				&:hover{
					background-color: $redColor;
					color: #fff;
				}
			}
			span:last-of-type{
				left: 135px;
			}
			button{
				width: 50px;
				height: 52px;
				outline: none;
				border: 1px solid #ccc; 
				margin-top: -1px;
				margin-right: -1px;
				position: absolute;
				right: 0;
				background-color: #fff;
				cursor: pointer;
				&:hover{
					background-color: $redColor;
					color: #fff;
					border: 1px solid $redColor; 
				}
				@include changeBorderColor;
			}
			.list{
				width: 247px;
				position: absolute;
				top: 100%;
				margin-left: -1px;
				border: 1px solid #ccc;
				@include changeBorderColor;
				z-index: 3;
				ul{
					background-color: #fff;
					li{
						width: 100%;
						height: 30px;
						line-height: 30px;
						cursor: pointer;
						&:hover{
							background-color: #efefef;
						}
						p{
							padding: 0;
							margin: 0;
							display: inline-block;
							padding: 0 8px;
							font-size: 12px;
							color: #666;
							&:last-of-type{
								float: right;
								color: #aaa;
							}
						}
					}
				}
			}
		}
		
	}
</style>