<template>
	<div id="server">
		<div class="w">
			<div class="top">
				<ul class="clearfix">
					<li v-for="val in topLi">{{ val }}</li>
				</ul>
			</div>
			<div class="bott clearfix">
				<div class="content" v-for="val in content">
					<ul class="clearfix">
						<p>{{ val.p }}</p>
						<li v-for="value in val.li">{{ value }}</li>
					</ul>
				</div>
				<div class="rightCon">
					<p v-for="val in rightCon">{{ val }}</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "server",
		data() {
			return {
				topLi: ["预约维修服务","7天无理由退货","15天免费换货","满150元包邮","520余家售后网点"],
				content: [
					{
						p: "帮助中心",
						li: ["账户管理","购物指南","订单操作"]
					},
					{
						p: "服务支持",
						li: ["售后政策","自助服务","相关下载"]
					},
					{
						p: "线下门店",
						li: ["小米之家","服务网点","零售网点"]
					},
					{
						p: "关于小米",
						li: ["了解小米","加入小米","联系我们"]
					},
					{
						p: "关注我们",
						li: ["新浪微博","小米部落","官方微信"]
					},
					{
						p: "特色服务",
						li: ["码通道","礼物码","防伪查询"]
					},
				],
				rightCon: ["400-100-5678","周一至周日 8:00-18:00","（仅收市话费）","24小时在线客服"]
			}
		}
	}
</script>

<style lang="scss">
	#server{
		width: 100%;
		.top{
			width: 100%;
			ul{
				border-bottom: 1px solid #ccc;
				li{
					float: left;
					width: 230px;
					margin: 30px 0;
					text-align: center;
					color: #888;
					border-right: 1px solid #ccc;
					cursor: pointer;
					&:last-of-type{
						border: none;
					}
					&:hover{
						color: #ff6700;
					}
				}
			}
		}
		.bott{
			.content{
				width: 150px;
				padding-bottom: 20px;
				float: left;
				ul{
					p{
						margin: 20px 0;
						font-size: 14px;
						color: #666;
					}
					li{
						width: 60px;
						margin: 15px 0;
						font-size: 12px;
						color: #999;
						cursor: pointer;
						&:hover{
							color: #ff6700;
						}
					}
				}
			}
			.rightCon{
				float: right;
				width: 252px;
				height: 112px;
				border-left: 1px solid #ccc;
				text-align: center;
				margin-top: 20px;
				p{
					color: #aaa;
					font-size: 12px;
					margin: 5px 0;
					&:nth-of-type(1){
						font-size: 18px;
						color: #ff6700;
					}
					&:nth-of-type(4){
						color: #ff6700;
						display: inline-block;
						margin-top: 10px;
						padding: 5px 15px;
						cursor: pointer;
						border: 1px solid #ff6700;
						&:hover{
							background-color: #ff6700;
							color: #fff;
						}
					}
				}
			}
		}
	}
</style>