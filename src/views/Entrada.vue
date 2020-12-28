<template>
<div class="entrada">
	<span>Entrada</span>
	<ComponenteEntrada/>
</div>
</template>

<script>
import Cliente from '@/components/Cliente.vue'
export default{
  components:{ComponenteEntrada:Cliente}
}
</script>
<style type="text/css">
	.entrada{
		margin: 10px;
		padding: 10px;
		background-color: #553f75;
		font-size: 2.6rem;
	}
</style>