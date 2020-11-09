<template>
  <v-app>
    <v-main>
      
      <EvenOrOdd/>
    </v-main>
  </v-app>
</template>

<script>
import EvenOrOdd from './components/EvenOrOdd';

export default {
  name: 'App',

  components: {
    EvenOrOdd,
  },

  data: () => ({
    //
  }),
};
</script>
