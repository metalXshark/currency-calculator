<template>
  <div id="app">
    <router-view /> <!-- Это рендерит текущий роут -->
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
/* Глобальные стили */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Arial', sans-serif;
  background-color: #f5f5f5;
  color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  flex-direction: column;
}

h1 {
  font-size: 2rem;
  color: #333;
  text-align: center;
  margin: 20px 0;
}
</style>
