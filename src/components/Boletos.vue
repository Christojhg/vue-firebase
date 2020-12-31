<template>
    <div class="section">
        <div class="atributo">
            <span> Boletos</span>
        </div>
        <div class="atributo">
            <span class="boletos">{{boletos}}</span>
        </div>
        <div class="atributo">
            <button @click="actualizarCantidad(1)">+</button>
            <button @click="actualizarCantidad(-1)">-</button>
        </div>
        <div class="atributo">
            <span class="comision" :class="claseComision" >${{comision}}</span>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            boletos:0,
            comision:0,
            claseComision:"neutro"

        }
    },
    methods:{
        actualizarCantidad(cantidad){
            this.boletos +=cantidad
            if(this.boletos >10){
                this.boletos=10
            }
            else if(this.boletos <0){
                this.boletos=0
            }
        }
        
    },
    watch:{
        boletos(newValue,oldValue){
            if(newValue > oldValue){
                this.comision +=10
            }else{
                this.comision -=15
            }
            if(this.comision < 0){
                this.comision=0
            }
        },
        comision(newValue,oldValue){
            if(this.comision == 0){
                this.claseComision="neutro"
            }
            else if(newValue>oldValue ){
                this.claseComision="incremento"
            }else{
                this.claseComision="decremento"
            }

        }
    }
}
</script>

<style>
.boletos{
    font-size:4rem;
    font-weight: bold;
}

.comision{
    font-size: 3rem;
}

.neutro{
    color: black;
}

.incremento{
    color: rgb(18, 196, 18);
}

.decremento{
    color:rgb(233, 10, 10);
}

</style>