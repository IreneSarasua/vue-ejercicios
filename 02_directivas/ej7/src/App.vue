<script setup>
import {ref} from 'vue'

const contador = ref(0);

const actualizarCont = (num) => {
    contador.value += num;
}

</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Contador</h2>

        <div class="alert alert-info" v-show="contador === 0">
            El contador es igual a cero.
        </div>
        <div class="alert alert-success" v-show="contador > 0">
            El contador es positivo: {{ contador }}
        </div>
        <div class="alert alert-warning" v-show="contador < 0">
            El contador es negativo: {{ contador }}
        </div>

        <div class="btn btn-primary me-1" @click="actualizarCont(1)">+</div>
        <div class="btn btn-primary ms-1" @click="actualizarCont(-1)">-</div>



    </div>
</template>

<style scoped>

</style>
