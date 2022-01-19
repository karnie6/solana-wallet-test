<template>
<wallet-provider :wallets="wallets">
    <wallet-modal-provider>
      <wallet-multi-button/>
    </wallet-modal-provider>  

    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App 2"/>

</wallet-provider>>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HelloWorld from './components/HelloWorld.vue';

import { getPhantomWallet, getSolflareWallet } from '@solana/wallet-adapter-wallets';
import { WalletMultiButton, WalletModalProvider } from '@solana/wallet-adapter-vue-ui';


// eslint-disable-next-line no-unused-vars
import { WalletProvider } from '@solana/wallet-adapter-vue';

// eslint-disable-next-line no-unused-vars
//const wallets =[];
const wallets = [
    getPhantomWallet(),
    getSolflareWallet(),
];  


@Options({
  components: {
    HelloWorld, WalletProvider, WalletMultiButton, WalletModalProvider

  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
