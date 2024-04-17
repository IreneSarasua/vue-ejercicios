<script setup>
import {ref} from 'vue'

//const miArray = ref([]);
const miArray = ref(['Elemento 1', 'Elemento 2', 'Elemento 3']);

</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Lista de elementos</h2>

        <ul class="list-group w-100">
            <li class="list-group-item d-flex justify-content-between align-items-center"
                v-for="elem of miArray">
                {{ elem }}
            </li>
        </ul>

        <div class="alert alert-danger" v-show="miArray.length === 0">
            No hay elementos en la lista.
        </div>


    </div>
</template>

<style scoped>

</style>
