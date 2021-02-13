<template>
  <div class="currency-converter">
      <h1>Currency Converter</h1>
      <h2>Convert from USD to {{ $store.state.rateObj.name }}</h2>
      <form class="convertForm">
          <label for = "amount">Enter amount to conver: </label>
          <input type="number" id="amount" name="amount"  v-model="amountToConvert"/>
      </form>
      <h2>{{ convertedAmount }}</h2>
  </div>
</template>

<script>
export default {
    data(){
        return{
            amountToConvert: ''
        }
    },
    computed: {
        convertedAmount() {
            return((this.amountToConvert * this.$store.state.rateObj.rate).toFixed(2));
        }
    }
}
</script>

<style>

</style>