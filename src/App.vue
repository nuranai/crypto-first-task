<template>
  <div class="app">
<!--    <img alt="Vue logo" src="./assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <ConnectWallet/>
    <Amount/>
    <Address/>
    <info/>
    <functionality/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ConnectWallet from "@/components/ConnectWallet";
import Amount from "@/components/Amount";
import Address from "@/components/Address";
import Info from "@/components/Info";
import Functionality from "@/components/Functionality";
import Web3 from "web3";
import Web4 from "@cryptonteam/web4";
import {ERC20} from "@/abis/abis";
import {tokens} from "@/utils/tokens";
import BigNumber from 'bignumber.js';

export default {
  name: 'App',
  components: {
    Functionality,
    Info,
    Address,
    Amount,
    ConnectWallet,
    // HelloWorld
  },
  async created() {

    const {ethereum} = window;
    let web3Wallet = new Web3(ethereum);
    if (await web3Wallet.eth.getCoinbase() === null) {
      await ethereum.enable();
    }
    let userAddress = await web3Wallet.eth.getCoinbase();
    let web4 = new Web4();
    await web4.setProvider(ethereum, userAddress)
    let erc20 = web4.getContractAbstraction(ERC20);

    // console.log()
    let instance1 = await erc20.getInstance(tokens.TOKEN_CFI);
    // let instance2 = await erc20.getInstance("0xc13da4146d381c7032ca1ed6050024b4e324f4ef");
    // let instance3 = await erc20.getInstance("0x8d0c36c8842d1dc9e49fbd31b81623c1902b7819");
    // let instance4 = await erc20.getInstance("0xa364f66f40b8117bbdb772c13ca6a3d36fe95b13");
    let decimals = await instance1.decimals();

    let balance = await instance1.balanceOf(userAddress)

    console.log(balance.toString());

    // let balance = await erc20.balanceOf("0x8d0c36c8842d1dc9e49fbd31b81623c1902b7819");

    // console.log(await instance1.allowance(userAddress, tokens.TOKEN_CFI ))

    // let balance = await web3Wallet.eth.getBalance(userAddress);

    console.log(await instance1.name(), await instance1.symbol(), await instance1.decimals())
    // console.log(await instance2.name(), await instance2.symbol(), await instance2.decimals())
    // console.log(await instance3.name(), await instance3.symbol(), await instance3.decimals());
    // console.log(await instance4.name(), await instance4.symbol(), await instance4.decimals());
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@700&display=swap');

.app {
  font-family: Roboto, sans-serif;
  font-size: 18px;
  font-weight: 400;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 1140px;
  margin: auto;
}
</style>
