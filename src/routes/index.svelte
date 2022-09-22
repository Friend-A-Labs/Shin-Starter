<script>
    // import transaction build from aptos sdk: https://github.com/aptos-labs/aptos-core/tree/main/ecosystem/typescript/sdk
import { BCS, TxnBuilderTypes } from 'aptos';

// Establish connection to the wallet
const result = await (window as any).aptos.connect()

// Check connection status of wallet
const status = await (window as any).aptos.isConnected()

// Gets the address of the account signed into the wallet
const accountAddress = await (window as any).aptos.account()

// Create a transaction
const transaction = {
    arguments: [address, '717'],
    function: '0x1::coin::transfer',
    type: 'entry_function_payload',
    type_arguments: ['0x1::aptos_coin::AptosCoin'],
};

// Send transaction to the extension to be signed and submitted to chain
const response = await (window as any).aptos.signAndSubmitTransaction(transaction)

// Send transaction to the extension to be signed and returns
const signedTransaction = await (window as any).aptos.signTransaction(transaction)

// Disconnect dApp from the wallet
await (window as any).aptos.disconnect(transaction)
</script>



<h1 class="text-lg font-sans text-red-300 p-4 ">Hello world!</h1>
<p class="text-md font-sans text-black p-4 pt-0">This is a basic starter for building web3 projects using svelte<br /><br />Click the button below to connect your wallet</p>
<a class="btn ml-4">Connect wallet</a>
