<template>
	<div id="sub">
		<div class="w clearfix">
			<div class="left">
				<div class="left-content" v-for="val in leftText">
					{{ val }}
				</div>
			</div>
			<div class="imgContent" v-for="val in imgArr">
				<a href="javascript:;" title="">
					<img :src="val" alt="">
				</a>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "mysub",
		data() {
			return {
				leftText: ["选购手机","企业团购","F码通道","米粉卡","以旧换新","话费充值"],
				imgArr: ["./src/assets/xmad_15091081421689_BOAey.jpg","./src/assets/xmad_15067798057483_gquZc.jpg","./src/assets/xmad_15064380498115_SqzKG.jpg"]
			}
		}
	}
</script>

<style lang="scss">
	#sub{
		width: 100%;
		margin-top: 15px;
		.left{
			width: 242px;
			height: 170px;
			background-color: #665e57;
			padding-top: 1px;
			float: left;
			.left-content{
				width: 33%;
				height: 49%;
				position: relative;
				float: left;
				text-align: center;
				line-height: 80px;
				font-size: 12px;
				color: #ccc;
				&:before{
					content: "";
					height: 70%;
					width: 1px;
					display: inline-block;
					background-color: #777;
					position: absolute;
					right: 0px;
					top: 15%;
				}
				&:nth-of-type(3):before,
				&:nth-of-type(6):before{
					width: 0px;
				}
				&:after{
					content: "";
					display: inline-block;
					background-color: #777;
					position: absolute;
					bottom: 0;
					height: 1px;
					left: 15%;
					width: 70%;
				}
				&:nth-of-type(4):after,
				&:nth-of-type(5):after,
				&:nth-of-type(6):after{
					height: 0px;
				}
			}
		}
		.imgContent{
			width: 316px;
			height: 170px;
			float: left;
			margin-left: 3px;
			a{
				display: inline-block;
				weight: 100%;
				height: 100%;
				img{
					weight: 100%;
					height: 100%;
				}
			}
		}
	}
</style>