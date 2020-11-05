<template>
  <v-app>
    <v-main>
      
      <PwdChange/>
    </v-main>
  </v-app>
</template>

<script>
import PwdChange from './components/PwdChange';

export default {
  name: 'App',

  components: {
    PwdChange,
  },

  data: () => ({
    //
  }),
};
</script>
