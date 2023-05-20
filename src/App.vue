<script setup>
import { ref, computed } from 'vue'


const users =  [
  {
    name:'Yair',
    lastname:'Rodriguez'
  },
  {
    name:'Pedro',
    lastname:'Gonzales',
    age:12 
  }
]

// const msg ="Perro careverga"
//const saludoBicho="Esto es para vosotros aficion"
//const siu="SIUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUUU"
const num = ref(0)
num.value = 2 //.value permite cambiar el valor de una constante en js

const mostrar = () => {
  console.log('Me estan llamando')
}
const computado = computed( ()=>{
  return num.value > 0 ? num.value*2: ""
}) 



</script>

<template>
  valor {{ num }} <br>
  {{ mostrar()}} <br>
 valor computado {{computado}}

 <div v-for="(user , index) in users" :key="index">
 Nombre completo :{{  user.name }} {{ user.lastname }} <br>
 <span v-if="user.age">
 Edad:  {{ user.age }}
 </span>
 </div>
</template>

<style scoped>

span{
  color:black;
}
span:hover{
  color:red;
}
div{
  color:yellowgreen;
}
div:hover{
  color:turquoise;
}

</style>
