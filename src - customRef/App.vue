<template>
  <input type="text" v-model="keyword">
  <h3>{{keyword}}</h3>
</template>

<script>
import {customRef} from 'vue'
export default {
  name:'app',
  setup(){
    let timer
    // 自訂義一個ref
    function myRef(value,delay) {
      return customRef((track,trigger)=>{
        return{
          get(){
            console.log(`有人從myREF讀取數據了,我把${value}給他了`)
            track() //通知vue追蹤value的變化(提前和getter商量一下讓他認為value是有用的)
            return value
          },
          set(newValue){
            console.log(`有人從myREF修改數據了,我把${newValue}給他了`)
            clearTimeout(timer)
            timer=setTimeout(()=>{
               value=newValue
                // 通知vue去重新解析模板
               trigger()
            },delay)
           
           
          }
        }
      })
    }
    //let keyword=ref('hello') //使用vue提供的ref
    let keyword=myRef('hello',500)  //使用程序員自訂的ref
    return{keyword}
  }
}
</script>

