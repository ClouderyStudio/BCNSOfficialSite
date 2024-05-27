<template>
	<div page>
		<banner :bg="'https://seati.oss-cn-qingdao.aliyuncs.com/assets/images/7.jpg'">
			<template #title> 捐助 BCNS </template>
			<template #subtitle> 帮助我们持续运行 </template>
			<template #text> BCNS 当前没有任何盈利项目，但接受无偿捐助，这能够维持 BCNS 的运行，也是 BCNS 的唯一收入。<br />你可以在本页面查看 BCNS 的资金运转情况和过往捐赠者信息。 </template>
		</banner>
		<div class="container">
			<div class="content typo">
				<h1 v-view.once="flowUp" class="primary-text">如何捐助</h1>
				<p v-view.once="flowUp">免责声明：<strong>未满 18 岁的未成年人请在家长同意后进行捐助，BCNS 从未教唆未成年人「为游戏充值」。捐助即代表你已经阅读并知晓该声明。</strong></p>
				<p v-view.once="flowUp">
					此处仅提供爱发电（爱发电内支持微信、支付宝）暂时不提供二维码，如需其它支付方式（不支持 QQ 支付）可联系服主。若要捐助，请前往爱发电，付款时<strong>请备注你的 Minecraft 用户名</strong>，以便我们写入鸣谢名单（低于
					<span class="money">￥5</span>
					的款项恕不写入）。支持
					<strong>5 天无理由全额退款</strong>，超过 5 天若仍因某些原因仍需退款可联系服主。<br/>
					<a v-view.once="flowUp" href="https://afdian.net/a/MagicQiyi" >点击前往 <strong>爱发电</strong></a>
				</p>
				

				<h1 v-view.once="flowUp" class="primary-text">感谢捐助</h1>
				<p v-view.once="flowUp">感谢这些人的无偿捐助，帮助了 BCNS 发展和维持运行。排名使用洗牌算法随机排列，刷新页面可重排。</p>
				<ul v-view.once="flowUp">
					<li v-for="(x, i) in shuffle(donators)" :key="i">
						{{ x.name }} —
						<span class="money">￥{{ x.amount }}</span>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
import Banner from '@/components/Banner.vue';
import { flowUp } from '@/fn';

export default Vue.extend({
	components: {
		Banner
	},
	data() {
		return {
			donators: [
				{
					name: '林与夕',
					amount: '200+'
				},
				{
					name: 'China1167',
					amount: 22.86
				},
				{
					name: 'NaziYa002',
					amount: 38.29
				},
				{
					name: '小空 (chenxiaoko)',
					amount: 7.62
				},
				{
					name: 'jie_geng_a (Ghost65576)',
					amount: 73.61
				},
				{
					name: 'Tmatsuki_rui',
					amount: 7.62
				},
				{
					name: '樱桃 (VocableJarl3651)',
					amount: 17.62
				},
				{
					name: 'Willow',
					amount: 7.62
				},
				{
					name: 'FBIYB',
					amount: 7
				},
				{
					name: 'huiaita',
					amount: 7.62
				},
			]
		};
	},
	methods: {
		flowUp,
		shuffle(array: Array<any>) {
			var m = array.length,
				t,
				i;
			while (m) {
				i = Math.floor(Math.random() * m--);
				t = array[m];
				array[m] = array[i];
				array[i] = t;
			}
			return array;
		}
	}
});
</script>

<style lang="less" scoped>
.pay {
	display: flex;
	align-items: center;
	justify-content: center;
	img {
		margin: 0 8px;
		height: 300px;

		@media (max-width: 800px) {
			height: 200px;
		}
	}
}
</style>