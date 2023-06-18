<template>
     <div class="container">
        <div class="left-container">
            <FrameOne :isMobile="isMobile"/>
            <FrameTwo :isMobile="isMobile"/>
        </div>
        <div class="right-container">
            <FrameThree v-if="!isMobile"/>
            <FrameFour :isMobile="isMobile"/> <!--Este siempre se va a mostrar-->
        </div>
     
    </div>
</template>

<script>
import {defineAsyncComponent} from 'vue'
export default {
    components:{
        FrameOne:defineAsyncComponent(()=>import('../components/FrameOne.vue')),
        FrameTwo:defineAsyncComponent(()=>import('../components/FrameTwo.vue')),
        FrameThree:defineAsyncComponent(()=>import('../components/FrameThree.vue')),
        FrameFour:defineAsyncComponent(()=>import('../components/FrameFour.vue'))
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
 .container{
    width: 93%;
    height: 110vh;
    margin:0 auto;
    display:flex;
 }
 .left-container, .right-container{
    height: 100%;
    width: 49%;
}
 .left-container{
    margin-right: 2%;
}

@media(max-width:450px){
    .container{
        height: auto;
        min-height: 160vh;
        flex-direction: column;
        margin-top: 50px;
    }
    .left-container, .right-container{
        height: 100%;
        width: 100%;
    }
    .left-container{
        margin-right: 2%;
    }
}
</style>