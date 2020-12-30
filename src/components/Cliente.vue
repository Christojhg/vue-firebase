<template>
<div class="section">
	<div class="atributo">
		<span>{{nombreCompleto}}</span>
	</div>
	<div class="atributo">
		<img v-bind:src="fotoPerfil">
	</div>
	<div class="atributo">
		<a v-bind:href="biografia" target="_blank">Biografia</a>
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
			fechaNacimiento:new Date(1994,9,27),
			fotoPerfil:'https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Sir_Isaac_Newton_%281643-1727%29.jpg/220px-Sir_Isaac_Newton_%281643-1727%29.jpg',
			biografia:'https://es.wikipedia.org/wiki/Isaac_Newton'
		}
	},
	computed:{
		nombreCompleto(){
			return `${this.nombres} ${this.apellidos}`
		},
		edad(){
			return this.calcularEdad(this.fechaNacimiento)
		}
	},
	methods:{
		calcularEdad(fecha){
			let fechaActual=new Date()
			let diferencia = fechaActual - fecha
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
	a{
		text-decoration: none;
		color:#553f75;
	}
</style>