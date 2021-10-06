<template>
  <div class="address">
    Address (recipient)<br/>
    <input type="text" v-model="addressValue" class="address__input input"/>
  </div>
</template>

<script>
// import Web3 from 'web3'
// import Web4 from '@cryptonteam/web4';
// import {ERC20} from "@/abis/abis";

export default {
  name: "Address",
  data: function() {
return {
    addressValue: '',
    erc20: undefined
};
},
  // methods:{
  //   toConsoleLog: async function () {
  //     console.log('starr')
  //     let instance = await this.erc20.getInstance("0x4b107a23361770534bd1839171bbf4b0eb56485c");
  //     console.log(await instance.name())
  //     console.log(await instance.symbol())
  //     console.log(await instance.decimals())
  //
  //   }
  // },
  // created: function () {
  //   const web4 = new Web4();
  //   web4.setProvider(new Web3.providers.HttpProvider("http://localhost:8545"))
  //   this.erc20 = web4.getContractAbstraction(ERC20);
  // }
}
</script>

<style scoped>
  .address {
    text-align: left;
  }

  .address__input {
    width: 1140px;
  }
</style>