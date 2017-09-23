<template>
  <div id="app">
    <v-header></v-header>
    <v-body></v-body>
    <v-foot></v-foot>
  </div>
</template>

<script>
  import header from './components/header/header';
  import body from './components/body/body';
  import foot from './components/foot/foot';

  export default {
    components: {
      'v-header': header,
      'v-body': body,
      'v-foot': foot
    }
  };

</script>

<style>

</style>
