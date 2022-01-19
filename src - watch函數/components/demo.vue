<template>
  <h2>當前求和為{{sum}}</h2>
  <button @click="sum++">點我+1</button>
  <hr>
  <h2>當前的訊息為{{msg}}</h2>
  <button @click="msg+='!'">修改訊息</button>
  <hr>
  <h2>人的姓名:{{person.name}}</h2>
  <h2>人的年齡:{{person.age}}</h2>
  <h2>薪資:{{person.job.j1.salary}}k</h2>
  <button @click="person.name+='~'">修改姓名</button>
  <button @click="person.age++">增加年齡</button>
  <button @click="person.job.j1.salary++">增加薪資</button>
</template>

<script>
import {ref,watch,reactive} from 'vue'
export default {
  name: 'demo',
  setup(){
    let sum=ref(0)
    let msg=ref('你好啊')
    let person=reactive({
      name:'張三',
      age:20,
      job:{
        j1:{
            salary:20
        }
      }
    })
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
    watch(()=>person.job,(newValue,oldValue)=>{
      console.log('person變化了',newValue,oldValue)
    }),{deep:false}
  return{
    sum,
    msg,
    person
  }
      // return ()=> h('h1','blibli')
 }
}
</script>

<style>

</style>
