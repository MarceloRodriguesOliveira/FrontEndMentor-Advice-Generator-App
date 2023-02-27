<template>
  <Advice/>
</template>

<script>
import Advice from './components/AdviceBox.vue'

export default {
  name: 'App',
  components:{
    Advice
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Manrope:wght@800&display=swap'); 
  *{
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
    font-family: 'Manrope';
  }

  body{
    background-color: hsl(218, 23%, 16%);
    padding: 1.25rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: calc(100vh - 0.1px);
    text-align: center;
  }

   @media(max-width:400px){
    body{
      min-width: 360px
    }
   }

</style>
