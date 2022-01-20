<template>
  <div class="son">
      <h3>我是孫子組件{{car.name}}--{{car.price}}</h3>
  </div>
</template>

<script>
import {inject} from 'vue'
export default {
    name:'son',
    setup(){
        let car=inject('carmsg')
        console.log(car,'@@@')
        return{car}
    }
}
</script>

<style>
    .son{
        background-color: pink;
        padding: 10px;
    }
</style>