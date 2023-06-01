<template>
   <div id="app"> 
   <h1> Le problème de Monty Hall </h1>
    <div class="form"> 
      <div v-if="!started">
          <label for="amountPorts"> Nombre de Portes?</label>
          <input type="text" id="amountPorts" size="3" v-model.number="amountPorts">
      
      </div>
     
      <button  v-if="!started"  @click="generateRandomNumber(amountPorts), started=true" >Démarrer</button>
       
      <button  v-if="started"  @click="started = false" >Redémarrer</button>
      
    </div>
    <div class="doors " v-if="started">
    <div v-for="i in amountPorts" :key="i"> 
        <DoorComponent :hasGift = "i==randomNumber" :number="i"/>
    </div>
    </div>
  </div>
</template>

<script>
import DoorComponent from './components/doorComponent'
export default {
  name :'App',
  components : {DoorComponent},
  data() {
    return {
      started :false,
      randomNumber: null,
      amountPorts : 3 ,
    };
  },
  methods: {
    generateRandomNumber(number) {
      this.randomNumber = Math.floor(Math.random() * number) + 1;
    }
  }


}
</script>

<style >
  *{
    box-sizing : border-box ;
    font-family: 'Poppins', sans-serif;
   
  }
    body{

      color : white ;
      background : linear-gradient(to right, #0f2027, #203a43, #2c5364);
    }
    #app {
      display : flex ;
      flex-direction : column;
      align-items : center;
    }
     #app h1 {
        border : 1px solid white ;
        padding : 20px ;
        margin-bottom :50 px; 

     }


     .form {

      display : flex;
      flex-direction: column;
      justify-content: center;
      align-items : center;
      margin-bottom: 30px;

     }

     .form, .form input, .form button {
      margin-bottom: 10px;
      font-size: 1.5rem;
     }
     .doors {
        display: flex;
        flex-direction: row;
        align-self: stretch;
        justify-content: space-around;
        flex-wrap: wrap;

     }
</style>