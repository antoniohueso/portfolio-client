<template>
  <div id="app">
    <div class="container">
      <h1 class="text-info">Sauron</h1>
    </div>
    <router-view/>
  </div>
</template>

<script>



export default {
  name: 'App'
}
</script>

<style>

  @import '../node_modules/bootstrap/dist/css/bootstrap.min.css';
  @import url('https://fonts.googleapis.com/css?family=Roboto+Condensed');
  @import url('https://fonts.googleapis.com/css?family=Roboto:300');

  body, html {
    font-family: Roboto, sans-serif; }

  h1, h2, h3, h4, h5, h6 {
    color: #6c757d; }

  legend {
    font-family: Roboto Condensed, sans-serif;
    color: #17a2b8; }

  label {
    font-family: Roboto Condensed, sans-serif;
    font-weight: bolder;
    color: #6c757d; }


</style>
