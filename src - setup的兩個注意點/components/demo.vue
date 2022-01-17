<template>
  <h2>姓名:{{person.name}}</h2>
  <h2>年齡:{{person.age}}</h2>
  <button @click="test1">測試觸發hello事件</button>
  <slot></slot>
</template>

<script>
import {reactive} from 'vue'
export default {
  name: 'demo',
  props:['msg','school'],
  emits:['hello'],
  setup(props,context){
    console.log(context.emit)
    console.log(context.slots)
    let person=reactive({
      name:'張三',
      age:20
    })
    function test1() {
        context.emit('hello',666)
    }
  return{
    person,test1
  }
      // return ()=> h('h1','blibli')
 }
}
</script>

<style>

</style>
