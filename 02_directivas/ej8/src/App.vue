<script setup>
import {ref} from 'vue'

const tareas = ref([
    {
        texto: 'Hacer la compra',
        completada: false
    },
    {
        texto: 'Hacer ejercicio',
        completada: true
    },
    {
        texto: 'Leer un libro',
        completada: false
    }
]);
const estiloPendiente = 'badge text-bg-primary rounded-pill';
const estiloCompletada = 'badge text-bg-secondary rounded-pill';

const actualizarTarea = (index) => {
    let tarea = tareas.value[index];

    if (tarea.completada){
        tareas.value.splice(index, 1);
    } else {
        tarea.completada = true;
    }


}
</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Lista de tareas</h2>
        <ul class="list-group w-100">
            <li class="list-group-item d-flex justify-content-between align-items-center"
                v-for="(elem, index) of tareas" :key="index" @dblclick="actualizarTarea(index)">
                {{ elem.texto }}

                <span :class="elem.completada ? estiloCompletada : estiloPendiente">
                    {{ elem.completada ?  'Completada': 'Pendiente'}}
                </span>

            </li>
        </ul>

    </div>
</template>

<style scoped>

</style>
