<template>
   <div class="component frame-one">
      <div class="header">
            <h2 class="title-header">Best Selling</h2>
            <div class="info-container">
               <p>This Week</p>
               <img src="../assets/icons/triangulo.png" alt="triangulo">
            </div>
            <div class="statistics-container">
               <p>Tuesday</p>
               <p>215,523 pcs</p>
            </div>
      </div>
      <div class="chart-container">
         <div class="chart-left">
            <img src="../assets/charts/pieCharts.png" alt="pie-chart">
         </div>
         <div class="chart-right" v-if="!isMobile">
            <div class="chart-right-container">
               <img class="bar-chart" src="../assets/charts/barChart-2.png" alt="bar-chart">
               <img class="leyenda" src="../assets/charts//leyenda.png" alt="leyenda">
            </div>
         </div>
      </div>
     
   </div>
</template>
<script>
export default{
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
    height: 52%;
    margin-bottom: 4%;
    width: 100%;
    border-radius: 20px;
  }
   .frame-one{
      background-color: rgb(39,46,53);
      color:rgb(255,255,255);
      margin-bottom: 30px;
   }
   .header{
      height: 25%;
      width:90%;
      border-radius: 20px;
      /* border:1px solid pink; */
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: flex-start;
      padding-top:20px;
      margin:0 auto;
   }
   .title-header{
      margin:0;
      font-weight: 500;
   }
   .info-container{
       /* border:1px solid pink; */
       display:flex;
       align-items: flex-start;
       gap:4px;
       color:rgb(183,183,183);
   }
   .info-container p{
      margin:0;
   }
   .info-container img{
      margin-top:7px;
   }
   .statistics-container{
      background-color: rgb(32,38,45);
      width: 100%;
      display:flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 7px;
      border-radius: 10px;
   }
   .statistics-container p{
      margin:0;
   }
   .chart-container{
      height: 75%;
      width:100%;
      display:flex;
   }
   .chart-left,.chart-right{
      width: 50%;
      border-radius: 20px;
      /* border:1px solid pink; */
   }
   .chart-left img{
      width:80%;
      display:block;
      margin:0 auto;
   }
   .chart-right-container{
      display: flex;
      flex-direction: column;
      align-items: center;
   }
   .bar-chart,.leyenda{
      width:70%;
   }
   @media(max-width:450px){
      .frame-one{
         margin-bottom: 30px;
         height: 450px;
      }
      .header{
         width:96%;
      }
      .chart-container{
         height: 220px;
         width:100%;
         display:block;
      }
      .chart-left{
         width:96%;
         margin:0 auto;
         height: 280px;
      }
      .chart-left img{
      width:90%;
   }
   }
</style>