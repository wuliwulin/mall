<template>
	<div class="carousel">
		<swiper :options="swiperOption" ref="mySwiper" @someSwiperEvent="callback">
    <!-- slides -->
	        <swiper-slide v-for="(item,index) in datas" :key="index"><img :src="item"></swiper-slide>
	    <!-- Optional controls -->
		    <div class="swiper-pagination"  slot="pagination"></div>
		   <!--  <div class="swiper-button-prev" slot="button-prev"></div>
		   <div class="swiper-button-next" slot="button-next"></div> -->
		    <div class="swiper-scrollbar"   slot="scrollbar"></div>
	    </swiper>
	</div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import {swiper,swiperSlide} from 'vue-awesome-swiper'
export default{
	name:"carousel",
  props:["datas"],
	components:{
		swiper,
		swiperSlide
	},
	data() {
      return {
        swiperOption: {
          pagination:{
          	el:'.swiper-pagination',
          	// clickable:true,
          	dynamicBullets:true
          },
          autoplay:{
          	// stopOnLastSlide:true,
          	delay:2500,
          	disableOnInteraction:false
          }
        }
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      }
    },
    mounted() {
      // current swiper instance
      // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
      console.log('this is current swiper instance object', this.swiper)
      this.swiper.slideTo(3, 1000, false)
    },
    methods:{
    }
}
</script>

<style lang="less" scoped>
  .carousel{
    height: 40%;
    width: 100%;
    img{
      height: 40%;
      width: 100%;
    }
  }
</style>