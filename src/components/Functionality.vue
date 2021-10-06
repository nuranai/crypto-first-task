<template>
  <div class="functionality">
    <get-allowance/>
    <approve/>
    <transfer/>
  </div>
</template>

<script>
import GetAllowance from "@/components/GetAllowance";
import Approve from "@/components/Approve";
import Transfer from "@/components/Transfer";
export default {
  name: "Functionality",
  components: {Transfer, Approve, GetAllowance}
}
</script>

<style scoped>
  .functionality {
    display: flex;

  }
</style>