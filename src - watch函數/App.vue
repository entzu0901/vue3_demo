<template>
  <demo>
    <template v-slot:schoolName>  
      <span>blibli</span>
    </template>
  </demo>
</template>

<script>
import demo from './components/demo.vue'
export default {
  components: { demo },
  name:'app',
}
</script>

