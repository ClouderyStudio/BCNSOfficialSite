<template>
	<div page>
		<banner :bg="'https://seati.oss-cn-qingdao.aliyuncs.com/assets/images/2.jpg'">
			<template #title> 加入 BCNS </template>
			<template #subtitle> 立即开始 </template>
			<template #text> 要加入 BCNS 与我们游戏，需要进入群聊。 </template>
		</banner>
		<div class="container">
			<div class="join content">
				<h1 class="primary-text" v-view.once="flowUp">立即加入 BCNS</h1>
				<p class="typo" v-view.once="flowUp"><strong>加入 QQ 交流群</strong>&emsp;我们的交流与讨论主要在 QQ 群内进行，我们强烈建议你加入~在这里你可以获取到第一手信息，获取帮助，并且可以参与到每周目的投票过程中。单击下方加群按钮可快速入群，或者搜索群号 588956007 亦可入群。</p>
				<p class="typo" v-view.once="flowUp"><strong>获取 BCNS测试服 白名单</strong>&emsp;若想要游玩抢先内容，需要获取 BCNS测试服 的白名单。要获取白名单，请前往问卷网填写问卷并等待人工审核，稍后通过邮件或者群内询问管理员的方式得到结果。<strong>注意: 测试服是不定期开放的。</strong></p>
				<div class="join-cards">
					<a class="join-card qq" href="https://qm.qq.com/cgi-bin/qm/qr?k=tcoJ_CF6AjAWGQS62TxGRIidea_4tqw7&jump_from=webapi" target="_blank">
						<mdicon name="arrow-right" />
						<img src="https://seati.oss-cn-qingdao.aliyuncs.com/assets/tencent-qq.svg" />
						<div class="text">
							<h1>QQ 讨论群</h1>
							<h2>点击加入，或搜索群号 588956007<br />验证信息请填写你的正版 ID</h2>
						</div>
					</a>
					<!--
					<a class="join-card wenjuan" href="https://www.wenjuan.com/s/UZBZJvcsEix" target="_blank">
						<mdicon name="arrow-right" />
						<img src="https://seati.oss-cn-qingdao.aliyuncs.com/assets/wenjuanwang.png" />
						<div class="text">
							<h1>白名单获取</h1>
							<h2>点击前往问卷网，填写 BCNS 玩家入服问卷以获取白名单</h2>
						</div>
					</a>
					-->
				</div>
				<p class="typo" v-view.once="flowUp">加入以后，请先认真阅读<strong>置顶群公告</strong>中的内容，这将指导你进行下一步操作。</p>
				<p class="typo" v-view.once="flowUp">
					如果你对插件有些生疏、不知道如何开始，或者有其它问题，你可以选择在<strong>群聊里询问</strong>，希望这可以让你快速解决问题:)
				</p>
			</div>
		</div>
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
import Banner from '@/components/Banner.vue';

import { flowUp, scaleIn, flowUpQuick, isPCSize } from '@/fn';
import anime from 'animejs';

export default Vue.extend({
	components: {
		Banner
	},
	methods: {
		flowUp,
		scaleIn,
		flowUpQuick,
		animateFeatureBox(e: ViewObject) {
			anime({
				targets: '.features .feature',
				opacity: [0, 1],
				translateY: [50, 0],
				duration: 750,
				easing: 'easeInOutExpo',
				delay: (el, i) => {
					return 150 * i;
				}
			});
		},
		isPCSize
	}
});
</script>

<style lang="less" scoped>
.join {
	.join-cards {
		margin: 16px 0;
		display: flex;
		align-items: stretch;
		@media (max-width: 1000px) {
			flex-direction: column;
		}

		.join-card {
			@media (min-width: 1000px) {
				width: 50%;
			}
			@media (max-width: 1000px) {
				margin: 8px 0;
			}

			.link-card;
		}
	}
}

.hero-box {
	p {
		color: @textlightgray;
		max-width: 600px;
		display: block;
		margin: auto;
	}
	margin-bottom: 64px;
	text-align: center;
}

.features {
	.feature-box {
		display: flex;
		@media (min-width: 1000px) {
			align-items: stretch;
		}
		@media (max-width: 1000px) {
			flex-direction: column;
		}
	}
}

.features {
	display: flex;
	flex-direction: column;

	.feature {
		@media (min-width: 1000px) {
			width: 33.333%;
			margin: 0 8px;
		}
		@media (max-width: 1000px) {
			margin: 8px 0;
		}
		text-shadow: @shadowlightx;
		box-shadow: @shadowlightx;

		&.black {
			background: #212121;
		}

		&.primary {
			background: @primaryg;
			p {
				color: @textlightgray;
			}
		}

		&.white {
			h1 {
				text-shadow: none;
				background: @primaryg;
				background-clip: text;
				color: transparent;
				display: inline-block;
			}
			p {
				color: @textlightgray;
				strong {
					color: @textgray;
				}
			}
			.mdi {
				svg {
					fill: @textgray;
				}
			}
			span {
				color: @textgray;
			}
		}

		&:first-child {
			margin-left: 0;
		}
		&:last-child {
			margin-right: 0;
		}
		border-radius: 12px;
		color: white;
		padding: 32px;

		h1 {
			margin-top: 0;
			margin-bottom: 8px;
			font-size: 40px;
		}

		p {
			font-size: 18px;
			z-index: 2;
		}
		overflow: hidden;
		.mdi {
			opacity: 0.4;
			position: absolute;
			right: 64px;
			bottom: 64px;
			transition: all 0.2s ease;
			z-index: 1;
			width: 24px;
			height: 24px;
			transform: scale(10);
		}

		position: relative;

		&:hover {
			.mdi {
				opacity: 0.7;
			}
		}

		> span:not(.mdi) {
			.monospace;
			position: absolute;
			opacity: 0.3;
			right: 32px;
			top: 32px;
		}
		opacity: 0;
	}
}
</style>