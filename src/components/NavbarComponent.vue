<template>
    <div>
        <nav class="relative px-4 py-4 flex justify-between items-center bg-white">
            
            <a class="text-3xl font-bold leading-none flex items-center" href="#">
                <img class="h-10" src="../images/Bitcoin_46999.ico">
                <span class="text-xl">BET-COIN.com</span>
            </a>
            <div class="lg:hidden">
                <button class="navbar-burger flex items-center text-blue-600 p-3" @click="toggleMenu">
                    <svg class="block h-4 w-4 fill-current" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                        <title>Mobile menu</title>
                        <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"></path>
                    </svg>
                </button>
            </div>
            <ul class="hidden absolute top-1/2 left-1/2 transform -translate-y-1/2 -translate-x-1/2 lg:flex lg:mx-auto lg:flex lg:items-center lg:w-auto lg:space-x-6">
                <li><a @click.prevent="changeCryptoSymbol('BTC')"class="text-sm text-gray-400 hover:text-gray-500" href="#">BTC</a></li>
                <li class="text-gray-300">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" class="w-4 h-4 current-fill" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v0m0 7v0m0 7v0m0-13a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
                    </svg>
                </li>
                <li><a @click.prevent="changeCryptoSymbol('ETH')"class="text-sm text-blue-600 font-bold" href="#">ETH</a></li>
                <li class="text-gray-300">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" class="w-4 h-4 current-fill" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v0m0 7v0m0 7v0m0-13a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
                    </svg>
                </li>
                <li><a @click.prevent="changeCryptoSymbol('LTC')"class="text-sm text-gray-400 hover:text-gray-500" href="#">LTC</a></li>
                <li class="text-gray-300">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" class="w-4 h-4 current-fill" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v0m0 7v0m0 7v0m0-13a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
                    </svg>
                </li>
                <li><a @click.prevent="changeCryptoSymbol('SOL')"class="text-sm text-gray-400 hover:text-gray-500" href="#">SOL</a></li>
                <li class="text-gray-300">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" class="w-4 h-4 current-fill" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v0m0 7v0m0 7v0m0-13a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
                    </svg>
                </li>
                <li><a @click.prevent="changeCryptoSymbol('XRP')"class="text-sm text-gray-400 hover:text-gray-500" href="#">XRP</a></li>
            </ul>
            <a class="hidden lg:inline-block py-2 px-6 bg-blue-500 hover:bg-blue-600 text-sm text-white font-bold rounded-xl transition duration-200" href="#">Sentiment Analysis</a>
        </nav>
        <div class="navbar-menu relative z-50" :class="{ 'hidden': !isMenuOpen }">
            <!-- Menu content here -->
            <button class="navbar-close" @click="toggleMenu">Close</button>
            <div class="navbar-backdrop fixed inset-0 bg-gray-800 opacity-25" @click="toggleMenu" v-if="isMenuOpen"></div>
            <nav class="fixed top-0 left-0 bottom-0 flex flex-col w-5/6 max-w-sm py-6 px-6 bg-white border-r overflow-y-auto">
                <div class="flex items-center mb-8">
                    <a class="mr-auto text-3xl font-bold leading-none" href="#">
                        <img class="h-10" src="../images/Bitcoin_46999.ico">
                    </a>
                    <button class="navbar-close" @click="toggleMenu">
                        <svg class="h-6 w-6 text-gray-400 cursor-pointer hover:text-gray-500" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                        </svg>
                    </button>
                </div>
                <div>
                    <ul>
                        <li class="mb-1">
                            <a @click.prevent="changeCryptoSymbol('BTC')"  class="block p-4 text-sm font-semibold text-gray-400 hover:bg-blue-50 hover:text-blue-600 rounded" href="#">BTC</a>
                        </li>
                        <li class="mb-1">
                            <a @click.prevent="changeCryptoSymbol('ETH')"  class="block p-4 text-sm font-semibold text-gray-400 hover:bg-blue-50 hover:text-blue-600 rounded" href="#">ETH</a>
                        </li>
                        <li class="mb-1">
                            <a @click.prevent="changeCryptoSymbol('LTC')"  class="block p-4 text-sm font-semibold text-gray-400 hover:bg-blue-50 hover:text-blue-600 rounded" href="#">LTC</a>
                        </li>
                        <li class="mb-1">
                            <a @click.prevent="changeCryptoSymbol('SOL')"  class="block p-4 text-sm font-semibold text-gray-400 hover:bg-blue-50 hover:text-blue-600 rounded" href="#">SOL</a>
                        </li>
                        <li class="mb-1">
                            <a @click.prevent="changeCryptoSymbol('XRP')"  class="block p-4 text-sm font-semibold text-gray-400 hover:bg-blue-50 hover:text-blue-600 rounded" href="#">XRP</a>
                        </li>
                    </ul>
                </div>
                <div class="mt-auto">
                    <div class="pt-6">
                        <a class="block px-4 py-3 mb-2 leading-loose text-xs text-center text-white font-semibold bg-blue-600 hover:bg-blue-700  rounded-xl" href="#">Sentiment Analysis</a>
                    </div>
                </div>
            </nav>
        </div>
    </div>
</template>

<script setup>
import { ref, inject } from 'vue';

// Inject the setCryptoSymbol method
const setCryptoSymbol = inject('setCryptoSymbol');

// Example method to change the crypto symbol
const changeCryptoSymbol = (symbol) => {
    setCryptoSymbol(symbol);
};

const isMenuOpen = ref(false);

function toggleMenu() {
    isMenuOpen.value = !isMenuOpen.value;
}

defineExpose({
    isMenuOpen,
    toggleMenu
});
</script>
