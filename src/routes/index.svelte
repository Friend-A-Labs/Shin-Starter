<script lang="ts">

    // import transaction build from aptos sdk: https://github.com/aptos-labs/aptos-core/tree/main/ecosystem/typescript/sdk
import { BCS, TxnBuilderTypes } from 'aptos';

let userAddress: String;

async function connectWallet(){
// Establish connection to the wallet
const result = await (window as any).aptos.connect()

// Check connection status of wallet
const status = await (window as any).aptos.isConnected()

// Gets the address of the account signed into the wallet
const accountAddress = await (window as any).aptos.account()

userAddress = accountAddress.address;

console.log(userAddress)

}

</script>
<h1 class="text-lg font-sans text-red-300 p-4 ">Hello world!</h1>
<p class="text-md font-sans text-black p-4 pt-0">This is a basic starter for building web3 projects using svelte<br /><br />Click the button below to connect your wallet</p>
<a class="btn ml-4" on:click={connectWallet}>Connect wallet</a>
<h1>{userAddress}</h1>
