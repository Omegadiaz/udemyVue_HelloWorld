<template>
  <button @click="aumentar"> {{ texto }}</button>
</template>

<script>
export default {
    props:{
        texto: String
    },
    methods: {
        aumentar(){
            this.$emit('accion')
        }
    }
}
</script>

<style>
    button{
        margin: 1em
    }
</style>