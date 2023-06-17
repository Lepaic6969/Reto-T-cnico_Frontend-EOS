<template>
  <div>
    <Navbar/>
    <Dashboard v-if="!isMobile"/>
  </div>
</template>

<script>
import {defineAsyncComponent} from 'vue'
export default {
    components:{
        Navbar:defineAsyncComponent(()=>import('../components/Navbar.vue')),
        Dashboard:defineAsyncComponent(()=>import('../components/Dashboard.vue'))
    },
    props:{
        isMobile:{
            type:Boolean,
            required:true
        }
    }
}
</script>

<style>

</style>