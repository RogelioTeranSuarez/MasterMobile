<template>
    <div v-if="showCookieBanner" class="cookie-banner">
      <p>Este sitio web utiliza cookies. Al hacer clic en "Aceptar", aceptas el uso de cookies.</p>
      <button @click="acceptCookies">Aceptar</button>
      <button @click="rejectCookies">Rechazar</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showCookieBanner: true
      };
    },
    methods: {
      acceptCookies() {
        this.showCookieBanner = false;
        // Aquí puedes agregar lógica para manejar la aceptación de cookies, como establecer una cookie o realizar una solicitud al servidor.
      },
      rejectCookies() {
        this.showCookieBanner = false;
        // Aquí puedes agregar lógica para manejar el rechazo de cookies, como mostrar información adicional o realizar otras acciones.
      }
    }
  };
  </script>
  
  <style scoped>
  .cookie-banner {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #f0f0f0;
    padding: 10px;
    text-align: center;
    box-shadow: 0px -1px 5px rgba(0, 0, 0, 0.2);
  }
  
  .cookie-banner button {
    margin: 0 5px;
    padding: 5px 10px;
    cursor: pointer;
  }
  </style>
  