<template>
  <h2>人的姓名:{{name}}</h2>
  <h2>人的年齡:{{age}}</h2>
  <h2>薪資:{{job.j1.salary}}k</h2>
  <button @click="name+='~'">修改姓名</button>
  <button @click="age++">增加年齡</button>
  <button @click="job.j1.salary++">增加薪資</button>
</template>

<script>
import {reactive,  toRefs} from 'vue'
export default {
  name: 'demo',
  setup(){
    let person=reactive({
      name:'張三',
      age:20,
      job:{
        j1:{
            salary:20
        }
      }
    })
    const x=toRefs(person)
    console.log('@@@',x)
    // watch([sum,msg],(newValue,oldValue)=>{
    //   console.log('sum的值發生變化了',newValue,oldValue),{
    //     immediate:true
    //   }
    // })
    // 情況三無法正確讀取到oldvalue參數 強制開啟深度監視(deep配置無效)
    // watch(person,(newValue,oldValue)=>{
    //   console.log('person變化了',newValue,oldValue)
    // }),{deep:false}
    // 情況四 監視reactive響應式數據的其中一個屬性
    // watch(()=>person.name,(newValue,oldValue)=>{
    //   console.log('person變化了',newValue,oldValue)
    // }),{deep:false}
    // 情況五 監視reactive響應式數據中的某些屬性
    // watch([()=>person.name,()=>person.age],(newValue,oldValue)=>{
    //   console.log('person變化了',newValue,oldValue)
    // }),{deep:false}
    // 特殊情況
  return{
    person,
    ...toRefs(person)
  }
      // return ()=> h('h1','blibli')
 }
}
</script>

<style>

</style>
