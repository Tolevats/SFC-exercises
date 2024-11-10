<template>
  <div id="app">
    <header>
      <h1>Ejercicios SFC</h1>
    </header>
    <FormsSFC />

    <footer>
      <p>Tolevats &copy; Copyright 2024</p>
    </footer>
  </div>
</template>

<script>
import FormsSFC from './components/FormsSFC.vue';

export default {
  name: 'App',
  components: {
   FormsSFC
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

h1 {
  margin: 2rem 1rem;
}

footer {
  margin-top: 10rem;
  font-size: 0.75rem;
  font-weight: bolder;
  font-style: italic;
  text-align: center;
}
</style>
