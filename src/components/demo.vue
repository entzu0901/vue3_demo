<template>
  <h2>當前求和為{{sum}}</h2>
  <button @click="sum++">點我+1</button>
  <hr>
  <h2>當前點擊的滑鼠座標為x:{{point.x}},y:{{point.y}}</h2>
</template>

<script>
import {ref} from 'vue'
import usePoint from '../hook/usepoint'
export default {
  name: 'demo',
  setup(){
    let sum=ref(0)
    let point=usePoint()
   return{sum,point}
  }
}
</script>