<template>
  <div class="popular-products">
    <h2 class="text-2xl font-bold mb-4">Productos populares</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-4">
      <div v-for="(product, index) in popularProducts" :key="index" class="bg-white p-4 rounded-lg shadow-md">
        <img :src="product.image" :alt="product.name" class="w-full h-32 object-cover mb-4">
        <h3 class="text-lg font-semibold mb-2">{{ product.name }}</h3>
        <p class="text-gray-600">{{ product.description }}</p>
        <div class="mt-4 flex justify-between items-center">
          <span class="text-red-600 font-bold">${{ product.price }}</span>
          <router-link to="/Producto/1" class="bg-red-600 text-white px-6 py-3 rounded-full font-semibold hover:bg-red-700"
            title="Producto">
            Comprar
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  data() {
    return {
      popularProducts: [
        {
          name: 'Dedales antisudor Razer',
          description: 'Razer Manga de Dedo para Videojuegos, Funda Antideslizante para Juegos móviles',
          image: './src/assets/producto_01.png',
          price: 603.13,
        }
        // Add more products as needed
      ],
    };
  },
  methods: {
    addToCart(product) {
      // Add your logic to handle adding the product to the cart
      console.log(`Added ${product.name} to the cart`);
    },
  },
};
</script>
  
<style scoped>
.popular-products {
  max-width: 1200px;
  margin-bottom: 10%;
  padding: 20px;
}

.popular-products h2 {
  color: #333;
}

.popular-products img {


  object-fit: cover;
}
</style>
  