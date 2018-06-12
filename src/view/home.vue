<template>
	<div class="home">
		<my-header></my-header>
		<carousel :datas="swiperData"></carousel>
		<activity :datas="activityData"></activity>
		<recommend :datas="recommendData"></recommend>
	</div>
</template>

<script>
import axios from "axios"
import MyHeader from "@/components/myHeader"
import Carousel from "@/components/carousel"
import Activity from "@/components/activity"
import Recommend from "@/components/recommend"
export default{
	name:'home',
	components:{
		MyHeader,
		Carousel,
		Activity,
		Recommend
	},
	data(){
		return {
			swiperData:{},
			activityData:{},
			recommendData:{},
		};
	},
	mounted(){
		this.getIndexData();
	},
	methods:{
		getIndexData(){
			axios.get("/api/index").then(res =>{
				let results = res.data
				this.swiperData = results.data.swiper
				this.activityData = results.data.activity
				this.recommendData = results.data.recommend

				//console.log(hhh);

				//console.log(results.data.swiper)
			})
		},
		toRequire(){
      }
	}
	
}
</script>

<style scoped></style>