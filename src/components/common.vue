<template>
	<div id="common">
		<div class="w" v-for="(con,conIndex) in content">
			<div class="header clearfix">
				<div class="left">{{ con.msg }}</div>
				<div class="right">
					<ul class="clearfix">
						<li v-for="(val,index) in con.liArr" :class="{current: val.hasClass}" @mouseenter="changeImg(index,conIndex)">{{ val.text }}</li>
					</ul>
				</div>
			</div>
			<div class="content clearfix">
				<div class="left">
					<div class="left-content-box" v-for="val in con.leftBox">
						<img :src="val" alt="">
					</div>
				</div>
				<div class="right">
					<div class="right-content" v-for="val in con.contentArr[con.oldIndex]">
						<span>{{ val.title }}</span>
						<img :src="val.url" alt="">
						<p>{{ val.p1 }}</p>
						<p>{{ val.p2 }}</p>
						<p>{{ val.p3 }}</p>
					</div>
					<div class="last-content">
						<div class="last-content-box" v-for="val in con.lastArr">
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
		name: "common",
		data() {
			return {
				content: [
					{
						msg: "智能",
						leftBox: ["./src/assets/xmad_1506079175852_RTDvC.jpg","./src/assets/xmad_15021710762698_QXnBu.jpg"],
						liArr: [
							{
								text: "热门",
								hasClass: true
							},
							{
								text: "出行",
								hasClass: false
							},
							{
								text: "健康",
								hasClass: false
							},
							{
								text: "酷玩",
								hasClass: false
							}
						],
						oldIndex: 0,
						contentArr: [
							[
								{
									title: "享9折",
									url: "./src/assets/pms_1501057018.70015369!220x220.jpg",
									p1: "小米AI音箱",
									p2: "",
									p3: "299元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1508724951.09887337!220x220.jpg",
									p1: "米家床头灯",
									p2: "如梦如幻，多彩光世界",
									p3: "249元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1508230324.1313855!220x220.jpg",
									p1: "小白智能摄像机大众版",
									p2: "看得更清，看得更远",
									p3: "109元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1506733860.3164711!220x220.jpg",
									p1: "车载空气净化器(USB车充版)",
									p2: "高效净化车内空气",
									p3: "449元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1488338229.6467773!220x220.jpg",
									p1: "米家行车记录仪",
									p2: "晚上能拍清车牌的行车记录仪",
									p3: "349元"
								},
								{
									title: "享9折",
									url: "./src/assets/T1PXhgBbdT1RXrhCrK!220x220.jpg",
									p1: "九号平衡车",
									p2: "年轻人的酷玩具，骑行遥控两种玩法",
									p3: "1999元"
								},
								{
									title: "享9折",
									url: "./src/assets/T1HQA_BCd_1RXrhCrK!220x220.jpg",
									p1: "米家iHealth血压计",
									p2: "爸妈上手就会用的智能血压计",
									p3: "399元"
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
					},
					{
						msg: "搭配",
						leftBox: ["./src/assets/xmad_14994014807425_VijLG.jpg","./src/assets/4c60cabb-d2c4-4fb6-bb06-3b35a8265932.jpg"],
						liArr: [
							{
								text: "热门",
								hasClass: true
							},
							{
								text: "耳机音箱",
								hasClass: false
							},
							{
								text: "电源",
								hasClass: false
							},
							{
								text: "电池存储卡",
								hasClass: false
							}
						],
						oldIndex: 0,
						contentArr: [
							[
								{
									title: "享9折",
									url: "./src/assets/pms_1505264799.43246303.jpg",
									p1: "小米AI音箱",
									p2: "",
									p3: "299元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1481269289.59498154.jpg",
									p1: "米家床头灯",
									p2: "如梦如幻，多彩光世界",
									p3: "249元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1476688193.46995320.jpg",
									p1: "小白智能摄像机大众版",
									p2: "看得更清，看得更远",
									p3: "109元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1482321212.47485716.jpg",
									p1: "车载空气净化器(USB车充版)",
									p2: "高效净化车内空气",
									p3: "449元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1478510064.36397738.jpg",
									p1: "米家行车记录仪",
									p2: "晚上能拍清车牌的行车记录仪",
									p3: "349元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1492587658.23552969.jpg",
									p1: "九号平衡车",
									p2: "年轻人的酷玩具，骑行遥控两种玩法",
									p3: "1999元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1502093110.00979492.jpg",
									p1: "米家iHealth血压计",
									p2: "爸妈上手就会用的智能血压计",
									p3: "399元"
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
								p1: "小米蓝牙耳机",
								p2: "59元",
								url: "./src/assets/pms_1478248721.42297795.jpg",
							},
							{
								p1: "浏览更多",
								p2: "热门",
								url: "./src/assets/ico.png",
							}
						]
					},
					{
						msg: "配件",
						leftBox: ["./src/assets/xmad_15030416937964_eOuQp.jpg","./src/assets/xmad_15053023729301_vkfBo.jpg"],
						liArr: [
							{
								text: "热门",
								hasClass: true
							},
							{
								text: "保护套",
								hasClass: false
							},
							{
								text: "贴膜",
								hasClass: false
							},
							{
								text: "其他配件",
								hasClass: false
							}
						],
						oldIndex: 0,
						contentArr: [
							[
								{
									title: "享9折",
									url: "./src/assets/pms_1503365520.83784737.jpg",
									p1: "  小米Note 3  智能立显半透保护套  ",
									p2: "",
									p3: "69元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1493261830.47158342.jpg",
									p1: "  小米6 硅胶保护套  ",
									p2: "",
									p3: "49元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1493863398.71652587.jpg",
									p1: "  小米6 弧边高透膜  ",
									p2: "",
									p3: "29元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1507555771.61081733.jpg",
									p1: "  MIX 2 标准高透膜  ",
									p2: "",
									p3: "39元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1493284697.69911065.jpg",
									p1: "  小米6 标准高透贴膜  ",
									p2: "",
									p3: "19元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1498547317.49155359.jpg",
									p1: "  小米6 超薄皮质保护套  ",
									p2: "",
									p3: "39元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1501555224.57453550.jpg",
									p1: "  小米5X 幻彩保护壳  ",
									p2: "",
									p3: "69元"
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
								p1: "小米6 高透软胶保护套",
								p2: "19元",
								url: "./src/assets/pms_1493261514.03223754.jpg",
							},
							{
								p1: "浏览更多",
								p2: "热门",
								url: "./src/assets/ico.png",
							}
						]
					},
					{
						msg: "周边",
						leftBox: ["./src/assets/xmad_15090666493096_nrpfl.jpg","./src/assets/xmad_15090668809491_TraoF.jpg"],
						liArr: [
							{
								text: "热门",
								hasClass: true
							},
							{
								text: "服装",
								hasClass: false
							},
							{
								text: "居家",
								hasClass: false
							},
							{
								text: "生活周边",
								hasClass: false
							}
						],
						oldIndex: 0,
						contentArr: [
							[
								{
									title: "享9折",
									url: "./src/assets/pms_1505375150.25573941!220x220.jpg",
									p1: "小米AI音箱",
									p2: "",
									p3: "299元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1502195257.33325849!220x220.jpg",
									p1: "米家床头灯",
									p2: "如梦如幻，多彩光世界",
									p3: "249元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1493030484.68163070!220x220.jpg",
									p1: "小白智能摄像机大众版",
									p2: "看得更清，看得更远",
									p3: "109元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1506329272.73789752!220x220.jpg",
									p1: "车载空气净化器(USB车充版)",
									p2: "高效净化车内空气",
									p3: "449元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1504521120.12574677!220x220.jpg",
									p1: "米家行车记录仪",
									p2: "晚上能拍清车牌的行车记录仪",
									p3: "349元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1472711253.2453066!220x220.jpg",
									p1: "九号平衡车",
									p2: "年轻人的酷玩具，骑行遥控两种玩法",
									p3: "1999元"
								},
								{
									title: "享9折",
									url: "./src/assets/pms_1507599833.28913942!220x220.jpg",
									p1: "米家iHealth血压计",
									p2: "爸妈上手就会用的智能血压计",
									p3: "399元"
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
								p1: "90分旅行箱",
								p2: "499元",
								url: "./src/assets/pms_1493873069.71028592!220x220.jpg",
							},
							{
								p1: "浏览更多",
								p2: "热门",
								url: "./src/assets/ico.png",
							}
						]
					},
				]
			}
		},
		methods: {
			// index: 鼠标移动到li的index值
			// conIndex: 鼠标当前所在content的index值
			changeImg(index,conIndex) {
				this.content[conIndex].liArr[index].hasClass=true;
				this.content[conIndex].liArr[this.content[conIndex].oldIndex].hasClass=false;
				this.content[conIndex].oldIndex=index;
					
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
	#common{
		width: 100%;
		padding-top: 30px;
		padding-bottom: 30px;
		background-color: #f5f5f5;
		.w{
			margin-top: 50px;
			margin-bottom: 50px;
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
					.left-content-box{
						width: 100%;
						height: 300px;
						@include shadow;
						margin-bottom: 14px;
						img{
							width: 100%;
							height: 100%;
						}
					}
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
	}
</style>