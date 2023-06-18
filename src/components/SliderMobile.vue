<template>
  <div>
    <swiper
    v-if="imgArr"
      :effect="'cards'"
      :grabCursor="true"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide><img class="image" :src='`${imgArr[13]}`' /></swiper-slide>
      <swiper-slide><img class="image" :src='`${imgArr[14]}`' /></swiper-slide><swiper-slide><img class="image" :src='`${imgArr[12]}`' /></swiper-slide>
      <swiper-slide><img class="image" :src='`${imgArr[7]}`' /></swiper-slide><swiper-slide><img class="image" :src='`${imgArr[3]}`' /></swiper-slide>
      <swiper-slide><img class="image" :src='`${imgArr[4]}`' /></swiper-slide><swiper-slide><img class="image" :src='`${imgArr[15]}`' /></swiper-slide>
      <swiper-slide><img class="image" :src='`${imgArr[17]}`' /></swiper-slide><swiper-slide><img class="image" :src='`${imgArr[18]}`' /></swiper-slide>
    </swiper>
    <Spinner v-else/>
  </div>
    
  </template>
  <script>
    // Import Swiper Vue.js components
    import { Swiper, SwiperSlide } from 'swiper/vue';
    import Spinner from '../components/Spinner.vue';
  
    // Import Swiper styles
    import 'swiper/css';
  
    import 'swiper/css/effect-cards';
  
    // import './style.css';
  
    // import required modules
    import { EffectCards } from 'swiper';
  
    export default {
      components: {
        Swiper,
        SwiperSlide,
        Spinner
      },
      setup() {
        return {
          modules: [EffectCards],
        };
      },
      data(){
        return {
            imgArr:null
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
    created(){
        this.getImages()
    }
};

  </script>
<style scoped>
.swiper-slide .image {
  width: 100%;
  transform: rotate(0deg); /* Rotación de 90 grados */
  transform-origin: center center;
}
.swiper {
  width: 240px;
  height: 320px;
}

.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 18px;
  font-size: 22px;
  font-weight: bold;
  color: #fff;
}

 .swiper-slide:nth-child(n) {
  background-color:    rgb(20,172,145);
  border:1px solid rgb(20,172,145);
}

</style>