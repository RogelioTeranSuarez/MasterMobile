<template>
    <Navbar />
    <div class="about-us">
        <h1 class="text-4xl font-bold mb-6">¿Quiénes somos?</h1>
        <img src="../assets/logo.png" class="h-80" alt="imagen del logo" title="Grow in box logo">
        <p class="text-lg mb-4">
            Bienvenido a Mobile Master! Estamos apasionados por ofrecerte lo mejor para que seas el mejor.
        </p>
        <p class="text-lg mb-4">
            Nuestra misión es traerte productos para juegos de dispositivos móviles que proporcionen una experiencia <span style="color: darkred;">legendaria</span>.
        </p>
        <p class="text-lg mb-8">
            Join us on this journey of blending creativity, style, and functionality to make every day a masterpiece.
        </p>
        <div>
            <h2 class="text-2xl font-bold mb-4">Nuestro equipo</h2>
            <ul>
                <li class="mb-2">Rogelio Yahir Terán Suárez - Fundador</li>
                <li class="mb-2">Rogelio Yahir Terán Suárez - Director creativo</li>
                <li class="mb-2">Rogelio Yahir Terán Suárez - Director de operaciones</li>
                <!-- Add more team members as needed -->
            </ul>
        </div>
    </div>
    <FooterComponent />
</template>

<script>
import Navbar from '../components/navbar.vue'
import FooterComponent from '../components/footer.vue'

export default {
    components: {
        Navbar,
        FooterComponent
    },
}
</script>

<style scoped>
.about-us {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  text-align: justify;
}

.about-us h1 {
  color: #7F0000;
}

.about-us p {
  color: #666;
}

.about-us h2 {
  color: #7F0000;
  margin-bottom: 1rem;
}

.about-us ul {
  list-style-type: none;
  padding: 0;
}

.about-us li {
  margin-bottom: 0.5rem;
}
</style>