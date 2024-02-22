<template lang="">
  <div class='for-border container-width'>
    <h1>Recipes</h1>
   <Pag></Pag>
  </div>
</template>
<script>
import Pag from './components/Pag.vue';
export default {
  components:{
    Pag
  }
}
</script>
<style>
  body{
    font-family: 'Inter', sans-serif;
  }
  h1{
    font-weight: 400px;
    font-size: 48px;
    
  }
  .container-width{
    width: 774px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>