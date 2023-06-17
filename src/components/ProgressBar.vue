<template>
    <n-progress
      type="line"
      :percentage="percentage"
      :indicator-placement="'inside'"
      color='rgb(19,180,151)'
      processing
    />
</template>
<script>
import {NProgress} from 'naive-ui'
export default {
    components:{
        NProgress
    },
    data(){
        return {
            percentage:20
        }
    },
    created(){
        setInterval(() => {
            if(this.percentage===100){
                this.percentage=15;
            }
            this.percentage+=5;
        }, 1000);
    }
}
</script>
<style scoped>
  .n-progress{
    width: 90%;
    margin: 0 auto;
    margin-top:30px;
    
  }
</style>