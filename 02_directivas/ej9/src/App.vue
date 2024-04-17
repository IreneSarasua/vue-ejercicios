<script setup>
import {ref, computed} from 'vue'

const mensajes = ref(
    [
        {
            texto: 'Mensaje 1',
            editando: false
        },
        {
            texto: 'Mensaje 2',
            editando: false
        },
        {
            texto: 'Mensaje 3',
            editando: false
        }
    ]
);

const modificarMensaje = (index) => {
    console.log('vaya....')
}
const borrarMensaje = (index) => {
    mensajes.value.splice(index, 1);
}

const estiloMensaje = 'w-100 border border-0 rounded focus-ring';
const estiloEditando = 'w-100 border border-0 rounded focus-ring bg-success bg-opacity-25';
const editar = (index) => {
    //mensajes.value[index].editando = !mensajes.value[index].editando;
    mensajes.value[index].editando = true;
    document.getElementById(index).readonly = false;
}

const noEditar = (index) => {
    mensajes.value[index].editando = false;
    document.getElementById(index).readonly = true;
}

</script>

<template>
    <div class="container w-50 pt-3">
        <h2>Mensajes</h2>
        <ul class="list-group w-100">
            <li class="list-group-item d-flex justify-content-between align-items-center"
                v-for="(elem, index) of mensajes" :key="index">
                <span class="w-100 h-100">
                    <!-- Como pone que se podra editar al hacer click, entiendo que deberia
                     ser la única forma de poder editarlo. Así evitamos acceder mediante tabulador
                     -->
                    <input :class="elem.editando? estiloEditando:estiloMensaje" :id="index"
                           v-model="elem.texto"
                           @focus="noEditar(index)" @focusout="noEditar(index)"
                           @click="editar(index)">

                </span>
                <span class="btn btn-primary rounded ms-2" @click="borrarMensaje(index)">
                    <i class="fa-regular fa-trash-can"></i>
                </span>

            </li>
        </ul>
    </div>
</template>

<style scoped>


</style>
