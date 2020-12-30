<template>
	<div>
		<span v-once>
			{{presentaciones[indice]}}
		</span>
	</div>
</template>

<script>
	export default{
		data(){
			return{
				presentaciones:[
					'Halmiton - 20:30',
					'Frozen - 15:15',
					'Rey León - 13:00',
					'Fish - 09:00'
				],
				indice:0
			}
		},
		methods:{
			mostrarAnuncio(){
				this.indice++
				if (this.indice == this.presentaciones.length) {
					this.indice=0
					this.$destroy()
				}
			}
		},
		beforeCreate(){
			console.log('beforeCreate')
		},
		created(){
			console.log('created')

		},
		beforeMount(){
			console.log('beforeMount')
		},
		mounted(){
			console.log('mounted')
			setInterval(this.mostrarAnuncio,2000)
			// this.mostrarAnuncio();
		},
		beforeUpdate(){
			console.log('beforeUpdate')
		},
		update(){
			console.log('update')
		},
		beforeDestroy(){
			console.log('beforeDestroy')
		},
		destroy(){
			console.log('destroy')
		},
	}
</script>