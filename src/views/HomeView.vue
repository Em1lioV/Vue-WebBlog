<template>
  <div class="home">
    home
    <p>my name is {{ name }} nad my age is {{ age }}</p>
    <button @click="handleClick">update</button>
    <h2>Refs</h2>
    <p>name: {{ playerOne.name }} - age: {{ playerOne.age }} - primitive: {{ nameOne }}</p>
    <button @click="updatePlayerOne">update</button>
    <h2>Reactive</h2>
    <p>name: {{ playerTwo.name }} - age: {{ playerTwo.age }} - primitive: {{ nameTwo }}</p>
    <button @click="updatePlayerTwo">update</button>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'


export default {
  name: 'HomeView',
  // this function will run before any of the life
  // cycle hooks
  setup() {
    /* ahora esto datos no estan linkeados a al template por lo que 
    si se actualizan no cambiara en el template */
    let name = 'emilio'
    let age = 20
    
    /* antes usabamos el this.$refs pero en la funcion setup esta no funciona */
    console.log(this) /* sera undefined */
    
    /* con la funcion ref podemos hacer estas variables reactivas a 
    los cambios en el template */
    const nameOne = ref('milio')
    const playerOne = ref({name:'emilio',age:'20'})

    const updatePlayerOne= () => {
      /* ahora necesitas agregar el .value para acceder a las valor del
      objeto ref */
      playerOne.value.age = 33
      /* se puden modificar valores primitivos */
      nameOne.value = 'dot'
    }
    
    /* otra forma de hacer estas variables reactibas  en el template
    es con reactive  */
    let nameTwo = reactive('mari')
    const playerTwo = reactive({name:'mariano',age:'18'})

    const updatePlayerTwo = () => {
      /* ahora no es necesario el .value */
      playerTwo.age = 33
      /* pero no se puede actualizar variables primitivas */
      nameTwo = 'mao'
    }


    const handleClick = () => {
      name = 'jorge' 
      age = 30 
      //no se ve el cambio en el template
    }

    return {name , age, handleClick, playerOne,playerTwo,nameOne,nameTwo,updatePlayerOne,updatePlayerTwo}


  }
}
</script>
