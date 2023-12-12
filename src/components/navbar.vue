<template>
    <nav className="bg-white m-5">
        <div className="flex space-x-4">
            <img src="../assets/logo.png" class="h-12" alt="imagen del logo" title="Grow in box logo">
            <router-link to="/"
                class="text-black hover:bg-red-800 hover:text-white px-3 py-3 rounded-md text-sm font-medium"
                title="home">Inicio</router-link>
            <router-link to="/aboutUs"
                className="text-black hover:bg-red-800 hover:text-white px-3 py-3 rounded-md text-sm font-medium"
                title="about">Sobre Nosotros</router-link>
            <router-link to="/catalogo"
                className="text-black hover:bg-red-800 hover:text-white px-3 py-3 rounded-md text-sm font-medium"
                title="catalogo">Catalogo</router-link>
        </div>
    </nav>
</template>

<script>
export default {
    name: "Navbar",
};
</script>