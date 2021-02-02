<template>
  <v-app>
    <v-main>
      <homeInsta/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import HomeInsta from './components/HomeInsta.vue';

export default {
  name: 'App',

  components: {
    HomeInsta,
  },

  data: () => ({
    //
  }),
};
</script>
