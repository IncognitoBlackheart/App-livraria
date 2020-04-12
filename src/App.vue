<template>
  <div id="app">
    <h1><p>App Livraria</p></h1>
    <AppLivraria />
    <Livraria />
    <BooksForm />
  </div>
</template>

<script>
import AppLivraria from './components/AppLivraria.vue'

export default {
  name: 'App',
  components: {
    AppLivraria
  }
}
</script>

<style scoped>
  p{
    text-align: center;
  }
</style>