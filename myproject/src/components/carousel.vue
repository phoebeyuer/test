<template>
	<div class="carousel">
		<swiper :options="swiperOption" ref="mySwiper">
    <swiper-slide><img src="../../static/carousel1.png"></swiper-slide>
    <swiper-slide><img src="../../static/carousel2.png"></swiper-slide>
    <swiper-slide><img src="../../static/carousel3.png"></swiper-slide>
    <swiper-slide><img src="../../static/carousel1.png"></swiper-slide>
    <swiper-slide><img src="../../static/carousel2.png"></swiper-slide>
    <swiper-slide><img src="../../static/carousel3.png"></swiper-slide>
    Optional controls
    <div class="swiper-pagination"  slot="pagination"></div>
	<div class="swiper-button-prev" slot="button-prev"></div>
	<div class="swiper-button-next" slot="button-next"></div>
	<div class="swiper-scrollbar"   slot="scrollbar"></div>
</swiper>
	</div>
</template>

<script>
import 'swiper/dist/css/swiper.css';
import { swiper,swiperSlide } from 'vue-awesome-swiper'; 
	export default{
		name: "carousel",
		components: {
			swiper,
			swiperSlide
		},
		data(){
			return{
				swiperOption: {
					pagination: {
						el: ".swiper-pagination",
						dynamicBullets: true
					},
					autoplay: {
						delay: 2500,
						disableOnInteraction: false
					}
				}
			};
		},
		computed: {
			swiper(){
				return this.$refs.mySwiper.swiper;
			}
		},
		mounted(){
			console.log("this is current swiper instance object",this.swiper);
			this.swiper.slideTo(3,1000,false);
		}
	};
</script>

<style lang="less" scoped>
	.carousel{
		display: block;
        color: black;
	}
</style>