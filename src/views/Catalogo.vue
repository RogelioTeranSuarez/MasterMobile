<template>
    <Navbar />

    <div class="container m-5">
        <h1 class="text-4xl">Productos</h1>

        <div class="grid grid-cols-3 gap-8">
            <div v-for="(producto, index) in productos" :key="index" class="card-container">
                <div class="relative flex flex-col rounded-xl bg-white bg-clip-border text-gray-700 shadow-md mt-10">

                    <div
                        class="relative mx-4 -mt-6 h-50 overflow-hidden rounded-xl bg-blue-gray-500 bg-clip-border text-white shadow-lg shadow-blue-gray-500/40">
                        <img :src="producto.imagen" alt="Product Image">
                    </div>

                    <div class="p-6">
                        <h5
                            class="mb-2 block font-sans text-xl font-semibold leading-snug tracking-normal text-blue-gray-900 antialiased">
                            {{ producto.nombre }}
                        </h5>
                        <p class="block font-sans text-base font-light leading-relaxed text-inherit antialiased">
                            {{ producto.descripcion_corta }}
                            <br>
                            <br>
                            <br>
                            <br>
                        </p>
                    </div>
                    <br>
                    <br>
                    <br>
                    <div class="p-6 mt-20 absolute bottom-0">
                        <router-link :to="{ name: 'Producto', params: { id: producto.id } }"
                            class="select-none rounded-lg bg-red-600 py-3 px-6 text-center align-middle font-sans text-xs font-bold uppercase text-white shadow-md shadow-pink-500/20 transition-all hover:shadow-lg hover:shadow-pink-500/40"
                            title="Producto">
                            Ver producto
                        </router-link>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <FooterComponent />
</template>

<script>
import Navbar from '../components/navbar.vue'
import FooterComponent from '../components/footer.vue'


import productosData from '../../productos.json';

export default {
    components: {
        Navbar,
        FooterComponent,
    },
    data() {
        return {
            productos: productosData.productos
        };
    }
}
</script>

<style scoped>
/* Estilo del grid */
.grid {
    display: grid;
}

/* Contenedor de las Cards */
.card-container {
    flex: 1;
    min-height: 100px;
    /* Tamaño mínimo de cada card? */
}
</style>