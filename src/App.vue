<template>
  <h1>一個人的訊息</h1>
  <h2>姓名:{{name}}</h2>
  <h2>年齡:{{age}}</h2>
  <h2>工作種類:{{job.type}}</h2>
  <h2>工作薪水:{{job.salary}}</h2>
  <button @click="change">修改人的訊息</button>
</template>

<script>
import { ref } from '@vue/reactivity'
export default {
  name: 'App',
  setup(){
    let name=ref('張三')
    let age=ref(20)
    let job=ref({
      type:"前端工程師",
      salary:'30k'
    })
    function change() {
     name.value="李四",
     age.value=30,
     job.value.type='UI設計師',
     job.value.salary="55k"
    }
    return{
      name,
      age,
      change,
      job
    }
      // return ()=> h('h1','blibli')
  }
}
</script>

<style>

</style>
