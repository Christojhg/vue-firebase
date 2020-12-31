<template>
<div class="section">
	<div class="atributo">
		<span>{{nombreCompleto}}</span>
	</div>
	<div class="atributo">
		<img :src="fotoPerfil">
	</div>
	<div class="atributo">
		<a :href="biografia" target="_blank">Biografia</a>
	</div>
	<div class="atributo">
		<span>Edad : {{edad}}</span>
	</div>
	<div class="atributo">
		<span>email : {{email}}</span>
	</div>
</div>
</template>

<script>
export default{
	props:['email'],
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
	},
	created(){
		this.$emit('onCambioEmail','email@email.com')
	}
}

</script>

<style scoped>
	
	
</style>