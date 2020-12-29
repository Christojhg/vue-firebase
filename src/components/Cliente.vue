<template>
<div class="section">
	<div class="atributo">
		<span>{{nombreCompleto}}</span>
	</div>
	<div class="atributo">
		<span>Edad : {{edad}}</span>
	</div>
</div>
</template>

<script>
export default{
	data(){
		return{
			nombres:"Issac",
			apellidos:'Newton',
			fechaNacimiento:new Date(1994,9,27)
		}
	},
	computed:{
		nombreCompleto(){
			return `${this.nombres} ${this.apellidos}`
		},
		edad(){
			let fechaActual=new Date()
			let diferencia = fechaActual - this.fechaNacimiento
			return Math.floor(diferencia/(1000*60*60*24*365))
		}
	}
}

</script>

<style scoped>
	.section{
		font-size:2.4rem;
	color:#202020;
	background-color:#e9e9e9;
	border-radius:5px;
	margin:10px;
	}
	.atributo{
		margin:10px;
	}
</style>