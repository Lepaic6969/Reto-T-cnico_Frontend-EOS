<template>
   
   <div class="component slider">
      <h1>Event Galleries</h1>
      <Slider class="slider-desktop" v-if="!isMobile"/>
      <SliderMobile v-else/>
      
      
      
   </div>
</template>

<script>
import Slider from '../components/Slider.vue'
import SliderMobile from './SliderMobile.vue'
export default {
   components:{
      Slider,
      SliderMobile
   },
   props:{
      isMobile:{
         type:Boolean,
         required:true
      }
   }
  
}
</script>

<style scoped>

.slider{
  height: 50%;
  margin-top:10%;
  background-color: rgb(47,54,61);
  position:relative;
 }
 h1{
   color:rgb(253,253,253);
   margin:0;
   top:-50px;
   margin-bottom:30px;
   font-weight: 500;
   letter-spacing: 1px;
   position:absolute;
 }
 


 @media(max-width:450px){
   .slider{
      height:300px;
      background: linear-gradient(to bottom, rgb(36,41,46), rgb(196,196,196));
   }
   h1{
      color:rgb(180,182,184);
      margin-top:0;
      letter-spacing: 0;
      text-align: center;
      font-weight: 300;
      font-size: larger;
      letter-spacing: 1px;
      margin-bottom: 30px;
      position:sticky;
 }
 }
</style>