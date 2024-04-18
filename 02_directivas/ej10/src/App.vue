<script setup>
import {ref, computed} from 'vue'

// const listaProd = ['Producto A', 'Producto B', 'Producto C', 'Producto D']
const listaProd = ref([
    {
        producto: 'Producto A',
        cantidad: 0
    },
    {
        producto: 'Producto B',
        cantidad: 0
    },
    {
        producto: 'Producto C',
        cantidad: 0
    },
    {
        producto: 'Producto D',
        cantidad: 0
    }
]);
//const misProd = ref([]);
const carroVacio = computed(() => {
    for (const elem of listaProd.value) {
        if (elem.cantidad !== 0) {
            return false
        }
    }
    return true
});
const prodNoVacio = computed(() => {
    let sol = []
    let i = 0;
    for (const elem of listaProd.value) {
        if (elem.cantidad !== 0) {
            //Voy a necesitar el indice en el array original
            elem["indice"] = i
            sol.push(elem)
        }
        i++;
    }
    return sol
});


const agregar = () => {
    let index = document.getElementById("productos").selectedIndex;
    listaProd.value[index].cantidad += 1;
}
const actualizrCant = (num, index) => {
    listaProd.value[index].cantidad += num;
}
const borrarProd = (index) => {
    listaProd.value[index].cantidad = 0;
}


</script>

<template>
    <div class="container w-50 pt-3">
        <h1>Carrito de la compra</h1>
        <ul class="list-group w-100">
            <li class="list-group-item d-flex justify-content-between align-items-center"
                v-for="(elem, index) of prodNoVacio" :key="index">
                <span>{{ elem.producto }} </span>

                <span class="badge text-bg-primary rounded-pill">{{ elem.cantidad }}</span>
                <div>
                    <span class="btn btn-secondary rounded ms-1" @click="actualizrCant(1, elem.indice)">
                    +
                    </span>
                    <span class="btn btn-secondary rounded ms-2" @click="actualizrCant(-1, elem.indice)">
                    -
                    </span>
                    <span class="btn btn-secondary rounded ms-2" @click="borrarProd(elem.indice)">
                    <i class="fa-regular fa-trash-can"></i>
                    </span>

                </div>


            </li>
        </ul>

        <div class="alert alert-danger" v-show="carroVacio">
            El carrito está vacio.
        </div>
        <h2 class="mt-3">Productos disponibles</h2>
        <div class="d-flex">
            <select name="productos" id="productos" class="form-select">
                <option v-for="(elem, index) of listaProd" :key="index"
                        :value="elem">{{ elem.producto }}
                </option>
            </select>
            <div class="btn btn-primary rounded ms-3 text-nowrap"
                 @click="agregar()">
                Agregar al carrito
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>
