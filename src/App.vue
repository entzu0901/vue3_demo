<template>
  <div class="app"> 
     <h3>我是app組件</h3>
     <child></child>
  </div>
</template>

<script>

import child from './components/child.vue'
export default {
  name:'app',
  components:{child},
 
}
</script>

<style>
  .app{
    background-color: gray;
    padding: 10px;
  }
</style>