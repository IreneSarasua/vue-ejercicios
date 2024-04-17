<script setup>
    import { ref } from 'vue';
    const datos = ref({
        nombre: '',
        apellido: ''
    })


</script>


<template>

    <div class="container w-50">
        <h2>Datos Personales</h2>
        <div class=" border border-1 border-black rounded p-3">
            <div class="mb-3">
                <label class="form-label" for="nombre">Nombre</label>
                <input class="form-control" id="nombre" type="text" v-model="datos.nombre" placeholder="Nombre"/>
            </div>
            <div class="mb-3">
                <label class="form-label" for="nombre">Apellido</label>
                <input class="form-control" id="nombre" type="text" v-model="datos.apellido" placeholder="Apellido"/>
            </div>
            <div class="alert alert-warning">
                Tu nombre completo es: {{ datos.nombre }} {{ datos.apellido }}
            </div>

        </div>
    </div>


</template>

<style scoped>

</style>
