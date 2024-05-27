<template>
	<div page>
		<banner bg="https://seati.oss-cn-qingdao.aliyuncs.com/assets/images/6.jpg">
			<template #title>关于 BCNS</template>
			<template #subtitle>了解更多</template>
			<template #text
				>在这里了解有关 BCNS 本身以及此网站的内容<br
			/></template>
		</banner>
		<div class="container content">
			<h1 class="primary-text" v-view.once="flowUp">BCNS 的历史</h1>
			<p v-view.once="flowUp" class="typo">
				<strong>BCNS</strong> 最初是在 2018
				年作为服主探索开服的一个简单项目出现的，其名称 <strong>云竹空岛</strong>。
				由于服主并没有开展宣传工作，加之内容单一，并没有招来很多玩家。后来又由于服主的现实原因，一直处于搁置状态。云竹空岛 初期实际上只能算是挂了个名号。
			</p>
		</div>
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
import Banner from '@/components/Banner.vue';
import { scaleIn, flowUp, flowLeft } from '@/fn';
export default Vue.extend({
	components: {
		Banner
	},
	methods: {
		scaleIn,
		flowUp,
		flowLeft
	}
});
</script>

<style lang="less" scoped>
.bad-design {
	width: 300px;
	display: block;
	margin-bottom: 32px;
}

.container {
	margin-bottom: 64px;
}
</style>