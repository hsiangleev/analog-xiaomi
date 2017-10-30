<template>
	<div id="app">
		<!-- 头部导航 -->
		<myheader></myheader>
		<!-- 导航条 -->
		<mynav></mynav>
		<!-- 轮播图 -->
		<home></home>
		<mysub></mysub>
		<!-- 小米明星单品 -->
		<single></single>
		<!-- 家电 -->
		<componcon></componcon>
		<common></common>
		<!-- 为你推荐 -->
		<recommend></recommend>
		<hotreview></hotreview>

		<server></server>
		<foot></foot>
	</div>
</template>

<script>

import myheader from "./components/header.vue";
import mynav from "./components/nav.vue";
import home from "./components/home.vue";
import mysub from "./components/sub.vue";
import single from "./components/single.vue";
import componcon from "./components/component.vue";
import common from "./components/common.vue";
import recommend from "./components/recommend.vue";
import hotreview from "./components/hotreview.vue";


import server from "./components/server.vue";
import foot from "./components/footer.vue";
export default {
	name: 'app',
	data () {
		return {
			
		}
	},
	components: {
		myheader,
		mynav,
		home,
		mysub,
		single,
		componcon,
		common,
		recommend,
		hotreview,
		
		server,
		foot
	}
}
</script>

<style lang="scss">

$redColor: #ff6700;
html,body{
	padding: 0;
	margin: 0;
	width: 100%;
}
#app {
	width: 100%;
}
.w{
	width: 1200px;
	margin: 0 auto;
}
ul{
	padding: 0;
	margin: 0;
	list-style: none;
}
a{
	text-decoration: none;
	color: #ccc;
}

</style>
