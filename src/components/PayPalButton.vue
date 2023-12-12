<template>
  <div>
    <div id="paypal-button-container"></div>
  </div>
</template>

<script>
import { loadScript } from "@paypal/paypal-js";

export default {
  props: {
    precio: {
      type: Number,
      required: true,
    },
  },
  mounted() {
    this.loadPayPalScript();
  },
  methods: {
    async loadPayPalScript() {
      try {
        // Carga el script del SDK de PayPal con el ID de PayPal
        const paypal = await this.loadScriptAsync();
        this.setupPayPalButton(paypal);
      } catch (error) {
        console.error("Failed to load the PayPal JS SDK script", error);
        // Maneja el error de carga del script de PayPal de manera más elegante si es necesario
      }
    },
    async loadScriptAsync() {
      try {
        return await loadScript({
          clientId: 'ARCm_a63Vg5nHPwvF1hsss9jUAxVmUTwLuX0EH316Syn2RCeRim7xHezUi_tetxSrZgmQPOZlioW695Z',
          currency: 'MXN'
        });
      } catch (error) {
        console.error("Failed to load the PayPal JS SDK script", error);
        throw error; // Rethrow the error or handle it as needed
      }
    },
    setupPayPalButton(paypal) {
      const { precio } = this;

      paypal.Buttons({
        createOrder: (data, actions) => {
          return actions.order.create({
            purchase_units: [
              {
                amount: {
                  value: precio.toFixed(2),
                },
              },
            ],
          });
        },
        onApprove: (data, actions) => {
          return actions.order.capture().then((details) => {
            console.log(details);
          });
        },
        onError: (err) => {
          console.error(err);
        },
      }).render('#paypal-button-container');
    },
  },
};
</script>
