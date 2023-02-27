<template>
    <div id="box-advice">
      <h5>Advice # {{idNumber}} </h5>
      <p>{{adviceTxt}}</p>
      <img src="../assets/pattern-divider-desktop.svg" alt="divider" id="img-divider">
      <div id="btn" @click="getAdvice">
        <img src="../assets/icon-dice.svg" alt="dice-icon">
      </div>
    </div>
</template>
  
<script>

export default {
  name: 'Advice',
  data(){
    return{
      idNumber:null,
      adviceTxt:null
    }
  },
  methods:{
    async getAdvice(){
      let req = await fetch('https://api.adviceslip.com/advice', {cache:"no-cache"})
      let data = await req.json()

      this.idNumber=data.slip.id
      this.adviceTxt=data.slip.advice
      
    }
  },
  mounted(){
    this.getAdvice()
  }
}
</script>

<style scoped>

  #box-advice{
    border-radius: 15px;
    background-color: hsl(217, 19%, 24%);
    position: relative;
    padding: 1.25rem 1.25rem 3rem;
    max-width: 600px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  #box-advice h5{
    color: hsl(150, 100%, 66%);
    margin-bottom: 10px;
  }

  #box-advice p{
    font-size: 28px;
    color: hsl(193, 38%, 86%);
    
    
    position: relative;
    line-height: 1.5;
    padding-bottom: 2rem;
    padding-top: 20px;
   
  }

  #box-advice #btn{
    width: 50px;
    height: 50px;
    margin: 0px;
    padding: 0px;
    border-radius: 100%;
    background-color: hsl(150, 100%, 66%);
    position: relative;
    border-color: 1px solid black;
    cursor: pointer;

    top: 4.5rem;
    align-self: center;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 99;
  }

  #btn:hover{
    box-shadow: 0px 0px 15px 5px hsl(150, 100%, 66%) ;
  }

  #btn img{
    width: 20px;
    height: 20px;

    
  }

  #img-divider{
    width: 100%;
    padding-top: 20px;
  }

 
</style>