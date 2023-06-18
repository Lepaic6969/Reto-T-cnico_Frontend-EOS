<template>
    <div class="spin-container">
        <n-spin :show="show">
            <template #icon>
                <n-icon>
                <Reload />
                </n-icon>
            </template>
        </n-spin>
        <h2 class='loading-animation'></h2>
    </div>
  
</template>
  
<script>
  import { ref, defineComponent } from "vue";
  import { Reload } from "@vicons/ionicons5";
  import {NSpin,NIcon} from 'naive-ui';
  
  export default defineComponent({
    components: {
      Reload,
      NSpin,
      NIcon
    },
    setup() {
      return {
        show: ref(false)
      };
    }
  });
</script>
<style scoped>
.spin-container{
    width:300px;
    /* border:1px solid white; */
    position:absolute;
    top:25%;
    left: 25%;
    margin: 10% auto;
    display:flex;
    justify-content: center;
}

h2{
    color:rgb(19,180,151);
    margin-left: 5px;
    text-shadow: 0 0 4px black;
}
@keyframes loading {
  0% {
    content: "Cargando";
  }
  50% {
    content: "Cargando.";
  }
  75% {
    content: "Cargando..";
  }
  100% {
    content: "Cargando...";
  }
}

.loading-animation::after {
  content: "Título";
  animation: loading 2s infinite;
}
@media(max-width:450px){
  .spin-container{
    width:300px;
    position:sticky;
    top:25%;
    left: 25%;
    margin: 10% auto;
    display:flex;
    justify-content: center;
}
}

</style>