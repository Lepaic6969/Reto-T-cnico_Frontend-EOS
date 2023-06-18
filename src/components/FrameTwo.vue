<template>
  <div class="component">
    <div class="chart-container">
      <div class="chart">
        <Header title="456k Pcs" period="Daily" description="Ticket Sold"/>
        <progress-bar/>
      </div>
       <div class="chart">
        <Header title="451,509" period="This Week" description="Sales"/>
        <img class="img-chart2" src="../assets/charts/curvas-1.png" alt="chart">
        <img class="dot" src="../assets/icons/dot.png" alt="dot">
        <img class="tooltip" src="../assets/icons/tooltip.png" alt="tooltip">
      </div>
      <div class="chart" v-if="!isMobile">
        <Header title="$456,623" period="Monthly" description="Income"/>
        <img class="img-chart3" src="../assets/charts/curvas-2.png" alt="chart">
   
      </div>
      <div class="chart pie-chart">
        <Header v-if="!isMobile" title="" period="This Week" description=""/>
        <img class="chart-pie" src="../assets/charts/pieChart.png" alt="pie-chart">
        <img v-if="!isMobile" class="legend-pie" src="../assets/charts/legend.png" alt="legend">
      </div>
    </div>

  </div>
</template>
<script>
import { defineAsyncComponent } from 'vue'
export default{
   components:{
    Header:defineAsyncComponent(()=>import('../components/HeaderChart.vue')),
    ProgressBar:defineAsyncComponent(()=>import('../components/ProgressBar.vue'))
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
  .component{
    height: 40%;
    margin-bottom: 4%;
    width: 100%;
    border-radius: 20px;
  }
  .chart-container{
    display:flex;
    flex-wrap:wrap;
    width: 100%;
    height: 100%;
    gap:1%;
  }
  .chart{
    width: 49%;
    height: 48%;
    border-radius: 20px;
    background-color: rgb(47,54,61);
    position:relative;
    overflow: hidden;
  }

  .img-chart2{
    width: 104%;
    margin: 0;
    position:absolute;
    bottom:-10px;
  }
  .img-chart3{
    width: 113%;
    margin: 0;
    position:absolute;
    bottom:-25px;
    left: -20px;
  }
  .chart-pie{
    position:absolute;
    bottom:10px;
    left: 10px;
    width:35%;
    
  }
  .legend-pie{
    width:50%;
    position:absolute;
    bottom:20px;
    right: 10px;
  }
  .dot{
    position:absolute;
    left:60%;
    top:62%;
  }
  .tooltip{
    position:absolute;
    left: 40%;
    top:35%;
    width: 40%;
  }
  @media(max-width:450px){
  .chart-container{
    flex-direction: column;
    width: 100%;
    height: auto;
  }
  .chart{
    width: 100%;
    height: 130px;
    margin-bottom: 20px;
  }
  .pie-chart{
    height: 200px;
  }
  .chart-pie{
    width:50%;
    top:50%;
    left: 50%;
    transform: translate(-50%,-50%); 
  }
  .dot{
    left:60%;
    top:55%;
  }
  .tooltip{
    left: 35%;
    top:25%;
    width: 40%;
  }
  }
</style>