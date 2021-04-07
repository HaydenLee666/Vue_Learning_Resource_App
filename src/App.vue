<template>
  <the-header :title="headerTitle"></the-header>
  <the-resource></the-resource>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResource from './components/learning-reasources/TheResource.vue';
export default {
  components: { TheResource, TheHeader },
  data() {
    return {
      headerTitle: 'Remember Me'
    };
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>