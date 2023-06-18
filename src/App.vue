<template>
  <div>
    <Header :isMobile="isMobile"/>
    <Content :isMobile="isMobile" :width="width"/>
  </div>
</template>

<script>
import {defineAsyncComponent} from 'vue'
export default {
  name: 'App',
  components: {
    Header:defineAsyncComponent(()=>import('@/views/Header.vue')),
    Content:defineAsyncComponent(()=>import('@/views/Content.vue'))
  },
  data(){
    return {
      isMobile:false, //Variable que me indica si estoy o no dentro de un dispositivo móvil.
      width:0 //Este es el ancho de la pantalla
    }
  },
  methods:{
    setIsMobile(){
      this.width=window.innerWidth
      if(window.innerWidth<=450){
        this.isMobile=true
      }else{
        this.isMobile=false
      }
    }
  },
  mounted() {
    window.addEventListener('resize', this.setIsMobile)
    this.width=window.innerWidth
    this.setIsMobile()
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.setIsMobile)
  },
}
</script>


