<template>
   <div class="child">
       <h3>我是child組件</h3>
       <son></son>
   </div>
</template>

<script>
import son from './son.vue'
export default {
    name:'child',
    components:{son},
}
</script>

<style>
    .child{
        background-color: skyblue;
        padding: 10px;
    }
</style>