<template>
  <button class="button">
    connect wallet
  </button>
</template>

<script>

export default {
  name: "ConnectWallet",
  data: function () {
    return {
      something: null
    }
  },
};
</script>

<style>
  .button {
    width: 187px;
    height: 50px;
    cursor: pointer;
    background-color: #63BCD8;
    border: none;
    color: white;
    font-size: 18px;
  }
</style>