<script setup>
import { ref } from 'vue';

let modulo1= ref('')


let turno1 = ref([])
let turno2 = ref([])
let turno3 = ref([])

let sizeTurno1 = ref(turno1.value.length)
let sizeTurno2 = ref(turno2.value.length)
let sizeTurno3 = ref(turno3.value.length)

let moduloselec = ref()

function recibeMoludo1 (){
  
  /*switch(moduloselec.value){
    case 'modulo 1':
      turno1.value.push(modulo1.value)
      sizeTurno1.value +=1
      break
    case 'modulo 2':
      turno2.value.push(modulo1.value)
      sizeTurno2.value +=1
      break
    case 'modulo 3':
      turno3.value.push(modulo1.value)
      sizeTurno3.value +=1
      break
    default:
      break
  }*/

  if(moduloselec.value == 'modulo 1'){
    turno1.value.push(modulo1.value)
    sizeTurno1.value +=1
  }

  if(moduloselec.value == 'modulo 2'){
    turno2.value.push(modulo1.value)
    sizeTurno2.value +=1
  }
  
  if(moduloselec.value == 'modulo 3'){
    turno3.value.push(modulo1.value)
    sizeTurno3.value +=1
  }
  
}

</script>

<template>
  
  <div class="bg-white shadow-black shadow-sm mx-auto h-auto w-[720px] mt-12 pt-16 pb-8 px-4">

    <div class="text-center mb-6 text-slate-700">
      <h1 class="font-semibold text-3xl h-auto">SISTEMA DE TURNOS</h1>
    </div>

    <div class=" flex py-4 h-auto justify-between">

      <div class="w-56">
        
        <div class="bg-blue-400 text-center h-auto p-4 rounded-xl rounded-b-none">
         <h1 class="font-semibold text-white text-xl">MODULO 1</h1>
        </div>

        <div class="bg-gray-300 rounded-xl rounded-t-none h-auto p-3">
          
          <div class="bg-white rounded-md py-1 px-4 mb-1" v-for="(i,index) in turno1" :key="index++">
            <h1 class="font-semibold">{{index}} - {{ i }}</h1>
          </div>
         
        </div>

      </div>

      <div class=" w-56">
        
        <div class="bg-yellow-400 text-center h-auto p-4 rounded-xl rounded-b-none">
         <h1 class="font-semibold text-white text-xl">MODULO 2</h1>
        </div>

        <div class="bg-gray-300 rounded-xl rounded-t-none h-auto p-3">
          
          <div class="bg-white rounded-md py-1 px-4 mb-1" v-for="(i,index) in turno2" :key="index++">
            <h1 class="font-semibold">{{index}} - {{ i }}</h1>
          </div>
          
        </div>
      </div>

      <div class="w-56">
        
        <div class="bg-green-500 text-center h-auto p-4 rounded-xl rounded-b-none">
         <h1 class="font-semibold text-white text-xl">MODULO 3</h1>
        </div>

        <div class="bg-gray-300 rounded-xl rounded-t-none h-auto p-3">
          
          <div class="bg-white rounded-md py-1 px-4 mb-1" v-for="(i,index) in turno3" :key="index++">
            <h1 class="font-semibold">{{index}} - {{ i }}</h1>
          </div>
          
        </div>

      </div>

    </div>

    <div class="bg-gray-300 flex p-6 rounded-md w-auto">
      
      <div class="flex p-2 ml-4">
        
        <div class="text-4xl my-auto mr-3 font-semibold">
          <h1>{{ sizeTurno1 + sizeTurno2 + sizeTurno3 }}</h1>
        </div>

        <div class="my-auto text-md font-semibold">
          <h1>Turnos</h1>
        </div>

      </div>

      <div class=" ml-16 p-2 flex">

        <input type="text" v-model="modulo1" class="rounded-lg border-gray-400 border-2 h-10 w-36 font-semibold p-2" placeholder="Código">

        <div class="ml-2 mr-2">
          <select name="hi" id="" v-model="moduloselec" class="rounded-lg border-gray-400 border-2 h-10 font-semibold pl-3 w-36">
            
            <option value="modulo 1">modulo 1</option>
            <option value="modulo 2">modulo 2</option>
            <option value="modulo 3">modulo 3</option>
          
          </select>
        </div>
        
        <button @click="recibeMoludo1" class="rounded-lg bg-purple-600 hover:bg-white hover:text-red-700 text-white h-10 font-semibold w-36 p-1 text-center">Agregar Turno</button>
       
      </div>

    </div>

  </div>

</template>


