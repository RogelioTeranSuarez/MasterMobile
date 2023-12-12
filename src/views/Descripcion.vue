<template>
    <Navbar></Navbar>

    <div class="container flex m-5">

        <div class="w-1/2 ml-20">
            
            <img :src="producto.imagen2"
                alt="Product Image" title="Imagen del producto" class="w-full h-auto object-cover object-center">
        </div>


        <div class="w-1/2 mr-10 font-medium">
            <h1 class="text-4xl ml-5">{{ producto && producto.nombre ? producto.nombre : '' }}</h1>
            <p class="mx-10 mt-15 font-medium text-justify">{{ producto && producto.descripcion_corta ? producto.descripcion_corta :
                '' }}</p>
            <p class="text-1xl ml-5 mt-6 ">$ {{ producto && producto.precio ? producto.precio : '' }} MXN</p>
            <p class="text-1xl ml-5 mt-6 ">Stock Disponible: {{ producto && producto.stock ? producto.stock : '' }}</p>

            <button class="bg-red-600 text-white my-5 mx-10 w-80 h-10" @click="showAlert">Agregar al
                carrito</button>
            <button class="mx-10 border-solid w-80 h-10">
                <PayPalButton :precio="producto && producto.precio ? producto.precio : 0"></PayPalButton>
            </button>

            <div class="wishlist">
                <span class="heart" :class="{ 'clicked': isClicked }" @click="toggleWishlist"></span>
            </div>

            
                <br>
                <br>
            <h2>Descripcion</h2>
                
<p class="mx-10 mt-15 font-medium text-justify justify-center">{{ producto && producto.descripcion ? producto.descripcion :
                '' }}</p>
        </div>
    </div>


    <div>
        
    </div>

</template>
    
<script>

import Navbar from '../components/navbar.vue'
import products from '../../productos.json';
import PayPalButton from '../components/PayPalButton.vue';

export default {
    name: 'ProductoUNO',
    data() {
        return {
            producto: {},
            isClicked: false
        };
    },
    methods: {
        showAlert() {
            alert('Producto agregado al carrito');
        },
        toggleWishlist() {
            this.isClicked = !this.isClicked; // Cambia el estado del corazón al hacer clic
        }
    },
    components: {
        Navbar,
        PayPalButton
    },
    created() {
        // Lógica para cargar los detalles del producto usando this.$route.params.id
        const productId = Number(this.$route.params.id); // Convertir a número
        console.log('productId:', productId);

        // Verifica si productId está definido y si el producto existe en el archivo JSON
        if (!isNaN(productId) && products.productos) {
            this.producto = products.productos.find(producto => producto.id === productId);
            console.log('Producto encontrado:', this.producto);
        }

        // Agrega una verificación adicional para asegurarte de que producto.nombre esté definido
        if (!this.producto || !this.producto.nombre) {
            console.error('Producto no encontrado o nombre no definido:', this.producto);
        }
    }
};
</script>