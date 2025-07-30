<template>
  <div class="currency-calculator">
    <div class="input-section">
      <label for="amount">Сумма</label>
      <input type="number" id="amount" v-model="amount" placeholder="Введите сумму" />

      <label for="from-currency">Из валюты</label>
      <select v-model="fromCurrency">
        <option v-for="currency in currencies" :key="currency" :value="currency">
          {{ currency }}
        </option>
      </select>

      <label for="to-currency">В валюту</label>
      <select v-model="toCurrency">
        <option v-for="currency in currencies" :key="currency" :value="currency">
          {{ currency }}
        </option>
      </select>

      <button @click="convertCurrency">Конвертировать</button>
    </div>

    <div v-if="convertedAmount !== null" class="result">
      <p>{{ amount }} {{ fromCurrency }} = {{ convertedAmount }} {{ toCurrency }}</p>
    </div>

    <div v-if="errorMessage" class="error">
      <p>{{ errorMessage }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      amount: 1,
      fromCurrency: 'USD',
      toCurrency: 'EUR',
      currencies: ['USD', 'EUR', 'GBP', 'JPY', 'AUD'],
      convertedAmount: null,
      errorMessage: null,
    }
  },
  methods: {
    async convertCurrency() {
      this.convertedAmount = null
      this.errorMessage = null

      try {
        const response = await axios.get(
            `https://api.exchangerate-api.com/v4/latest/${this.fromCurrency}`
        )
        const rate = response.data.rates[this.toCurrency]
        this.convertedAmount = (this.amount * rate).toFixed(2)
      } catch (error) {
        this.errorMessage = 'Ошибка при получении данных. Попробуйте снова позже.'
      }
    },
  },
}
</script>

<style scoped>
.currency-calculator {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 30px;
  width: 350px;
  text-align: center;
}

.input-section {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

label {
  font-size: 1rem;
  color: #555;
  margin-bottom: 5px;
}

input,
select {
  padding: 10px;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  outline: none;
  transition: border-color 0.3s;
}

input:focus,
select:focus {
  border-color: #007bff;
}

button {
  margin-top: 20px;
  padding: 12px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
}

button:hover {
  background-color: #0056b3;
}

.result {
  margin-top: 20px;
  font-size: 1.2rem;
  color: #333;
}

.error {
  color: red;
  margin-top: 10px;
  font-size: 1rem;
}
</style>
