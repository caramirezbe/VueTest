<template>
  <v-app>
    <v-main>

      <!--      <EvenOrOdd/>-->

      <Datatime/>
    </v-main>
  </v-app>
</template>

<script>
// import EvenOrOdd from './components/EvenOrOdd';
import Datatime from "@/components/DataTime";

export default {
  name: 'App',

  components: {
    Datatime,
    // EvenOrOdd,
  },

  data: () => ({
    //
  }),
};
</script>
