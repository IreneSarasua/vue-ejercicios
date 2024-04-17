<script setup>
import {ref} from 'vue';

const mensaje = ref('');
const cont = ref(0);

const contarCarac = () => {
    cont.value = mensaje.value.length;
}
</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Contar Caracteres</h2>
        <div class=" border border-1 border-black rounded p-3">
            <div class="mb-3">
                <label class="form-label" for="mensaje">Mensaje</label>
                <input class="form-control" id="mensaje" type="text" v-model="mensaje" @keyup="contarCarac()" placeholder="Escribe un mensaje"/>

            </div>
            <div class="alert alert-warning d-flex justify-content-between">
                <span v-if="cont === 0">Escribe algo...</span>
                <span v-else>Mensaje: {{ mensaje }}</span>
                <span class="badge text-bg-primary rounded-pill">{{ cont }}</span>
            </div>


        </div>
    </div>
</template>

<style scoped>

</style>
