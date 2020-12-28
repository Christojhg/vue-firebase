<template>
  <div id="app" class="principal">
    <span>App</span>
    <entrada />
  </div>
</template>

<script>
import Entrada from '@/views/Entrada.vue'
export default{
  components:{Entrada}
}
</script>


<style>

html{
  font-size:62.5% ! important;
}

.principal{
  background-color:#a21010;
  padding:10px;
  color:white;
  border-radius:5px;
  width:400px;
  font-size:3rem;
  text-align:center;
}
</style>
