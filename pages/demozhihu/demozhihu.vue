<template>
	<view style="width: 100%;height: 100%;">
		<ezflycard
			@onDragMove='onCardDragMove'
			@onDragStop='onCardDragStop'
			@onThrowDone='onCardThrowDone'
			:cardWidth="300" 
			:cardHeight="120"
			:throwTriggerDistance="100"
			dragDirection="horizontal"
			:hasShadow="true"
		>
			<view slot="firstCard" style="width:100%;height:100%;">
				<view v-if="cards[0]" class="zhihuCard">
					<view>{{cards[0].title}}</view>
					<view>
						<view>{{cards[0].followcount}} 关注</view>
						<view>
							<button disabled="">忽略</button>
							<button type="primary">回答</button>
						</view>
					</view>
				</view>
			</view>
			<view slot="secondCard" style="width:100%;height:100%;">
				<view v-if="cards[1]" class="zhihuCard">
					<view>{{cards[1].title}}</view>
					<view>
						<view>{{cards[1].followcount}} 关注</view>
						<view>
							<button disabled="">忽略</button>
							<button type="primary">回答</button>
						</view>
					</view>
				</view>
			</view>
			<view slot="thirdCard" style="width:100%;height:100%;">
				<view v-if="cards[2]" class="zhihuCard">
					<view>{{cards[2].title}}</view>
					<view>
						<view>{{cards[2].followcount}} 关注</view>
						<view>
							<button disabled="">忽略</button>
							<button type="primary">回答</button>
						</view>
					</view>
				</view>
			</view>
		</ezflycard>
	</view>
</template>

<script>
	import ezflycard from "../../components/ezflycard.vue"
	export default {
		components:{
			ezflycard
		},
		data() {
			return {
				title: 'Hello',
				cards:[
					{
						title:"js数组怎么遍历删除指定元素，最后全部删除？",
						followcount:6
					},
					{
						title:"前端自学，前后端的交互应该学哪些，要重点学哪里？",
						followcount:13
					},
					{
						title:"我们花那么多时间在游戏《塞尔达传说：旷野之息》里，到底得到了什么？",
						followcount:29
					},
					{
						title:"跪求这个图片用HTML，CSS如何做出来？",
						followcount:6
					}
				]
			}
		},
		onLoad() {

		},
		methods: {
			onCardDragMove(obj){
				
			},
			onCardDragStop(obj){
				
			},
			onCardThrowDone(obj){
				this.cards.splice(0,1);
			}
		}
	}
</script>

<style>
	page{
		width: 100%;
		height: 100%;
		overflow: hidden;
	}
	
	view{
		box-sizing: border-box;
	}
	.zhihuCard{
		padding: 10px;
	}
	.zhihuCard:nth-child(1)
	{
		font-size: 18px;
	}
	.zhihuCard>view:nth-child(2)
	{
		display: flex;
		position: absolute;
		width: 100%;
		left:0px;
		bottom: 10px;
		padding:0px 10px;
	}
	.zhihuCard>view:nth-child(2)>view:nth-child(1)
	{
		flex:1;
		font-size: 14px;
		color: #666;
	}
	.zhihuCard>view:nth-child(2)>view:nth-child(2)
	{
		display: flex;
	}
	.zhihuCard>view:nth-child(2)>view:nth-child(2)>button:nth-child(2)
	{
		margin-left: 5px;
	}
	button
	{
		height: 24px;
		line-height: 24px;
		font-size: 12px;
	}
</style>
