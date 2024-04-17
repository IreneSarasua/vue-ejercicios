<script setup>
    import { ref } from 'vue';
    const  mostrar = ref(false);
    const cambioEstado = () => {
        mostrar.value = !mostrar.value
    }

</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Mensaje oculto</h2>

        <div class="alert alert-success" v-show="mostrar">
            ¡Hola, este es un mensaje!
        </div>
        <div class="btn btn-primary" @click="cambioEstado()">
            Mostrar/Ocultar mensaje
        </div>
    </div>
</template>

<style scoped>

</style>
