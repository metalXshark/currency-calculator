<template>
  <div class="home">
    <h1>Калькулятор валют</h1>
    <CurrencyCalculator />
  </div>
</template>

<script>
import CurrencyCalculator from '@/components/CurrencyCalculator.vue'

export default {
  name: 'Home',
  components: {
    CurrencyCalculator,
  },
}
</script>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 50px;
}

h1 {
  font-size: 2rem;
  color: #333;
  margin-bottom: 20px;
}
</style>
