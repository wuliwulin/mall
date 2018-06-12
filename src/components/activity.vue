<template>
	<div class="activity">
		<h3 class="title">活动推荐</h3>
		<div class="content">
			<div class="content-item" v-for="(item,index) in datas" :key="index">
				<img :src="item.img">
				<p class="name">{{item.name}}</p>
				<p class="desc">{{item.desc}}</p>
			</div>
		</div>
	</div>
</template>

<script>
export default{
	name:"activity",
	props:["datas"],
	data(){
		return{
			items:[
			{},{}
			]
		};
	},
	mounted(){}
}
</script>

<style lang="less" scoped>
	.activity{
		background: #eee;
		.title {
			width:100%;
			height: 50px;
			line-height: 50px;
			text-align: center;
			color: gray;
			border-bottom: 1px solid gray;
			background: #fff;
		}
		.content{
			.content-item{
				background: #fff;
				margin-bottom: 10px;
				img{
					width: 100%;
					height: 150px;
				}
				.name{
					font-size: 15px;
					color: #000;
					margin-bottom: 5px;
				}
				.desc{
					font-size: 13px;
					color: #000;
				}
			}
		}
	}
</style>