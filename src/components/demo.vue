<template>
  <h1>一個人的訊息</h1>
  姓:<input type="text" v-model="person.firstName">
  <br>
  名:<input type="text" v-model="person.lastName">
  <br>
  <span>全名:{{person.fullName}}</span>
  <br>
  全名:<input type="text" v-model="person.fullName">  
</template>

<script>
import {reactive,computed} from 'vue'
export default {
  name: 'demo',
  setup(){
    let person=reactive({
      firstName:'張',
      lastName:'三'
    })
    person.fullName=computed({
        get(){
            return person.firstName+'-'+person.lastName
        },
        set(value){
            const nameArr=value.split('-')
            person.firstName=nameArr[0]
            person.lastName=nameArr[1]
        }
    })
  return{
    person
  }
      // return ()=> h('h1','blibli')
 }
}
</script>

<style>

</style>
