<template>
  <demo @hello="showHelloMsg" msg="你好啊" school='blibli'>
    <template v-slot:schoolName>  
      <span>blibli</span>
    </template>
  </demo>
</template>

<script>
import demo from './components/demo.vue'
export default {
  components: { demo },
  name:'app',
  setup(){
    function showHelloMsg(value){
      alert(`你好啊:${value}`)
    }
    return{showHelloMsg}
  }
}
</script>

