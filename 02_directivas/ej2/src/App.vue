<script setup>
import {ref} from 'vue';

const prueba = ref(false);

const estilo1 = {
    backgroundColor: '#555555'
}
const estilo2 = {
    backgroundColor: '#82005e'
}

const cambio = () =>{
    prueba.value = !prueba.value;
    console.log(prueba.value)
}

</script>

<template>
    <div class="container pt-5">
        <h1 :class="prueba? '':'border border-1 rounded'" >Practica con v-bind</h1>
        <p   class="text-info" :style="prueba? estilo1:estilo2">Este es ejemplo práctico con v-bind en Vue 3.</p>
        <a :href="prueba? '#':'index.html'" @click="cambio()">Ir al ejemplo</a>
    </div>
</template>

<style scoped>


</style>
