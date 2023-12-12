<template>
    <div class="bg-[url('./src/assets/producto_01.png')] text-white min-h-screen flex items-center justify-center">
        <div class="text-center">
            <h1 class="text-4xl font-bold mb-4">Master Mobile</h1>
            <p class="text-lg mb-8">Consigue todo lo que necesites para ser Legendario</p>
            <div class="flex justify-center">
                <router-link to="/catalogo"
                            class="bg-red-600 text-white px-6 py-3 rounded-full font-semibold hover:bg-red-700"
                            title="Producto">
                            Comprar
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>

export default{


}
</script>