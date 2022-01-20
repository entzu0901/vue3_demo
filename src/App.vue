<template>
  <div class="app"> 
     <h3>我是app組件,{{name}}--{{price}}</h3>
     <child></child>
  </div>
</template>

<script>
import { reactive,toRefs,provide } from 'vue'
import child from './components/child.vue'
export default {
  name:'app',
  components:{child},
  setup(){
    let car=reactive({
      name:'aaa',
      price:'335k'
    })
    provide('carmsg',car)
    return {...toRefs(car)}
  }
}
</script>

<style>
  .app{
    background-color: gray;
    padding: 10px;
  }
</style>