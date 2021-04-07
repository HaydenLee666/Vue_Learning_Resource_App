<template>
  <the-header :title="headerTitle"></the-header>
  <stored-resources :resources="storedResources"></stored-resources>
</template>

<script>
import StoredResources from './components/learning-reasources/StoredResources.vue';
import TheHeader from './components/layouts/TheHeader.vue';

export default {
  components: { StoredResources, TheHeader },
  data() {
    return {
      headerTitle: 'Remember Me',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official Vue.js documentation.',
          link: 'https://vue.js.org'
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google..',
          link: 'https://www.google.com.au/'
        }
      ]
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