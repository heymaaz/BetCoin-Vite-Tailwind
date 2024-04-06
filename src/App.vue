<script setup>
// Import ref and provide from Vue
import { ref, provide } from 'vue';

// Setup a reactive reference for the crypto symbol
const cryptoSymbol = ref('BTC'); // Default value

// Provide the cryptoSymbol so it can be injected in descendants
provide('cryptoSymbol', cryptoSymbol);

// Optionally, provide a method to update this symbol
const setCryptoSymbol = (symbol) => {
    cryptoSymbol.value = symbol;
};
provide('setCryptoSymbol', setCryptoSymbol);

import NavbarComponent from './components/NavbarComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';


</script>

<template>
  <NavbarComponent />
  <MainComponent />
  <FooterComponent />
</template>

