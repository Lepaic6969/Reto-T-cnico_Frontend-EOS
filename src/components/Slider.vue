<template>
    <div>
        <swiper
            v-if="imgArr"
            :effect="'coverflow'"
            :grabCursor="true"
            :centeredSlides="true"
            :slidesPerView="'auto'"
            :coverflowEffect="{
                rotate: 50,
                stretch: 0,
                depth: 100,
                modifier: 1,
                slideShadows: true,
            }"
            :pagination="true"
            :modules="modules"
            class="mySwiper"
        >
                <swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[0]:imgArr[13]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[1]:imgArr[14]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[2]:imgArr[12]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[3]:imgArr[7]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[4]:imgArr[3]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[5]:imgArr[4]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[6]:imgArr[15]}`' /></swiper-slide
                ><swiper-slide
                    ><img
                    :src='`${correctArray?arrDefault[7]:imgArr[17]}`' /></swiper-slide
                ><swiper-slide
                    ><img :src='`${correctArray?arrDefault[8]:imgArr[18]}`'
                /></swiper-slide>
        </swiper>
        <Spinner v-else/>
    </div>
</template>
  <script>
  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from "swiper/vue";
  
  // Import Swiper styles
  import "swiper/css";
  
  import "swiper/css/effect-coverflow";
  import "swiper/css/pagination";
  
  // import required modules
  import { EffectCoverflow, Pagination } from "swiper";
  import Spinner from '../components/Spinner.vue'
  export default {
    components: {
      Swiper,
      SwiperSlide,
      Spinner
    },
    props:{
        width:{
            type:Number,
            required:true
        }
    },
    setup() {
      return {
        modules: [EffectCoverflow, Pagination],
      };
    },
    data(){
        return {
            imgArr:null,
            arrDefault:[
                "https://swiperjs.com/demos/images/nature-1.jpg",
                "https://swiperjs.com/demos/images/nature-2.jpg",
                "https://swiperjs.com/demos/images/nature-3.jpg",
                "https://swiperjs.com/demos/images/nature-4.jpg",
                "https://swiperjs.com/demos/images/nature-5.jpg",
                "https://swiperjs.com/demos/images/nature-6.jpg",
                "https://swiperjs.com/demos/images/nature-7.jpg",
                "https://swiperjs.com/demos/images/nature-8.jpg",
                "https://swiperjs.com/demos/images/nature-9.jpg"
            ]
        }
    },
    methods:{
     async getImages(){
        try{
            const resp=await fetch('https://picsum.photos/v2/list?page=2&limit=100')
            const images=await resp.json()
            this.imgArr=images.map(img=>img.download_url)
        }catch(err){
            console.log(err)
        }
     }
    },
    computed:{
        correctArray(){
            return (this.width>=1280);
        }
    },
    created(){
        this.getImages()
    }
  };
  </script>
<style scoped>
.swiper {
  padding-top: 50px;
  padding-bottom: 50px;
}

.swiper-slide {
  background-position: center;
  background-size: cover;
  width: 300px;
  height: 300px;
}

.swiper-slide img {
  display: block;
  width: 100%;
}
</style>