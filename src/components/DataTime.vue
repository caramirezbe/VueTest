<!-- - Read a date (day month year). (Bonus: use <v-date-picker>)
    Show time between that day and today.
    Show day of the week (write your own function).
    Show is leap year (write your own function)
    (Bonus) Show if it's the first week of the month. -->


<template>
  <v-container>
    <v-toolbar flat color="blue">
      <v-toolbar-title>Problems</v-toolbar-title>
    </v-toolbar>
    <v-form>
      <v-row>
        <v-col cols="4">
          <v-date-picker
              v-model="date1"
          ></v-date-picker>
          <v-date-picker
              v-model="date2"
          ></v-date-picker>
          <v-btn @click="strDate()"
                 class="primary">Submit
          </v-btn>
        </v-col>
        <v-col cols="4">
          {{ message }}
        </v-col>


      </v-row>
    </v-form>
  </v-container>
</template>

<script>
export default {
  name: 'DataTime',

  data() {
    return {
      date1: "2020-04-20",
      date2: new Date().toISOString().substr(0, 10),
      message: 'Hola',
    }
  },

  methods: {

    strDate() {
      const d = new Date(this.date1); // Convert string to date
      // let iy = this.date1.replace(/-/gi, '').substr(0, 4)
      // let im = this.date1.replace(/-/gi, '').substr(5)
      // let id = this.date1.replace(/-/gi, '').substr(6, 8)
      // console.log('year ' + iy)
      // console.log('month ' + im)
      // console.log('day ' + id)
    },

  }


}
</script>>
