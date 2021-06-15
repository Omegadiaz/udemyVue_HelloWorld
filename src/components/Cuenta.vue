<template>
  <h1>Cuenta</h1>
    <h3>Saldo {{cantidad}}</h3>
    <AccionSaldo texto="Aumentar" @accion="aumentar"/>
    <AccionSaldo texto="Disminuir" :disabled="desactivar" @accion="disminuir"/>
</template>

<script>
import AccionSaldo from "./AccionSaldo.vue";
export default {
    components: {
        AccionSaldo
    },
    name: "Cuenta",
    data() {
        return {
            cantidad: 1000,
            desactivar: false
        }
    },
    methods: {
        aumentar(){
            this.cantidad = this.cantidad + 100
        },
        disminuir() {
            this.cantidad = this.cantidad - 100
        }
    },
    updated(){
        if(this.cantidad === 0){
            this.desactivar = true
        }else{
            this.desactivar = false
        }
    }  
    
}
</script>

<style scoped>
    h1 {
        color: peru;
    }
</style>