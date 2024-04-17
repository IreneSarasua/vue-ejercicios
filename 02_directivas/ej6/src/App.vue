<script setup>
import {ref} from 'vue'

const campo1 = ref('');
const campo2 = ref('');

</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Vlaidación</h2>
        <div class=" border border-1 border-black rounded p-3">
            <div class="mb-3">
                <input class="form-control" id="campo1" type="text"
                       placeholder="Campo 1" v-model="campo1"/>

            </div>
            <div class="mb-3">
                <input class="form-control" id="campo2" type="text"
                       placeholder="Campo 2"  v-model="campo2"/>

            </div>
            <div class="alert alert-warning" v-show="campo1.length === 0 || campo2.length === 0">
                Completa ambos campos.
            </div>
            <div class="alert alert-success" v-show="campo1.length !== 0 && campo2.length !== 0">
                Ambos campos están llenos.
            </div>

        </div>
    </div>
</template>

<style scoped>

</style>
