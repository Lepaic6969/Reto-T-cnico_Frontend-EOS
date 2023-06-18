<template>
    <div>
        <div class="header">
            <h2 class="title-header">{{ title }}</h2>
            <div class="info-container">
                <p>{{ period }}</p>
                <img src="../assets/icons/triangulo.png" alt="triangulo">
            </div>
        </div>
        <p class="description">{{ description }}</p>
    </div>

 
</template>

<script>
export default {
    props:{
        title:{
            type:String,
            required:true
        },
        period:{
            type:String,
            required:true
        },
        description:{
            type:String,
            required:true
        }
    }

}
</script>

<style scoped>
    .header{
      height: 25%;
      width:90%;
      border-radius: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: flex-start;
      padding-top:20px;
      margin:0 auto;
      color:rgb(255,255,255);
   }
   .title-header{
      margin:0;
      font-weight: 500;
      font-size:18px;
   }
   .info-container{
       display:flex;
       align-items: flex-start;
       gap:8px;
       color:rgb(183,183,183);
   }
   .info-container p{
      margin:0;
   }
   .info-container img{
      margin-top:10px;
   }
   .description{
    color:rgb(183,183,183);
    margin:0;
    margin-left: 12px;
   }
   
</style>