<template>
<div class="anuncio">
	<anuncio/>
	<cliente/>
</div>
</template>

<script>
import Cliente from '@/components/Cliente.vue'
import Anuncio from '@/components/Anuncio.vue'
export default{
  components:{cliente:Cliente,Anuncio:Anuncio}
}
</script>

<style>

.anuncio{
	margin:10px;
	font-size: 2rem;
	border-top-color:white;
	border-top-width: 1px;
	border-top-style:solid;

	border-bottom-color:white;
	border-bottom-width: 1px;
	border-bottom-style:solid;
}
</style>
