<template>
  <div class="amount">
    <p>Amount</p>
    <div class="amount__wrapper">
      <input class="amount__input input" type="text" value="0.0"/>
      <select class="amount__select">
        <option class="amount__option">BUSD</option>
        <option class="amount__option">ETH</option>
        <option class="amount__option">BTC</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "Amount"
}
</script>

<style>

  .amount {
    text-align: left;
  }

  .amount__wrapper {
    display: flex;
  }

  .input {
    height: 70px;
    background-color: #F3F5FA;
    font-size: 24px;
    border: none;
  }

  .amount__input {
    width: 966px;
  }

  .amount__select {
    box-sizing: content-box;
    font-size: 24px;
    font-weight: 700;
    padding-left: 28px;
    color: white;
    appearance: none;
    width: 144px;
    height: 70px;
    margin: 0;
    background-color: #63BCD8;
    background-image: url("../assets/arrow-vector.svg");
    background-repeat: no-repeat;
    background-position: 75.5% 50%;
    border: none;
  }
</style>