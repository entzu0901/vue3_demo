<template>
  <div class="son">
      <h3>我是孫子組件</h3>
      <talk></talk>
  </div>
</template>

<script>
import talk from './talk.vue'
export default {
    name:'son',
    components:{talk}
}
</script>

<style>
    .son{
        background-color: pink;
        padding: 10px;
    }
</style>