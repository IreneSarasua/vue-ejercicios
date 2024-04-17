<script setup>
import {ref, computed} from 'vue';

const mensaje = ref('');

const contarCaracteres = computed(() => {
    return mensaje.value.length
})
</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Contar Caracteres</h2>
        <div class=" border border-1 border-black rounded p-3">
            <div class="mb-3">
                <label class="form-label" for="mensaje">Mensaje</label>
                <input class="form-control" id="mensaje" type="text" v-model="mensaje"
                       placeholder="Escribe un mensaje"/>

            </div>
            <div class="alert alert-warning d-flex justify-content-between">
                <span v-if="mensaje.length === 0">Escribe algo...</span>
                <span v-else>Mensaje: {{ mensaje }}</span>
                <span class="badge text-bg-primary rounded-pill">{{ contarCaracteres }}</span>

            </div>


        </div>
    </div>
</template>

<style scoped>

</style>
