<!-- - Read a date (day month year). (Bonus: use <v-date-picker>)
    Show is leap year (write your own function) listo 
    Show time between that day and today. 
    Show day of the week (write your own function).listo 
    (Bonus) Show if it's the first week of the month. -->


<template>
  <v-container>
    <v-toolbar flat color="blue">
      <v-toolbar-title>Problems</v-toolbar-title>
    </v-toolbar>
    <v-form>
      <v-row>
        <v-col cols="4">
          <v-date-picker v-model="picker1"></v-date-picker>
          <v-date-picker v-model="picker2"></v-date-picker>
          <v-btn @click="yearInformation()"
                 class="primary">Submit
          </v-btn>
        </v-col>
        <v-col cols="4">
         <v-alert> {{leapYear1Message}}</v-alert>
         <v-alert> {{leapYear2Message}}</v-alert>
         <v-alert> {{beteweenD}}</v-alert> 
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
      picker1: new Date().toISOString().substr(0, 10),
      picker2: new Date().toISOString().substr(0, 10),
      leapYear1Message:'',
      leapYear2Message:'',
      weekday:['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'],
      beteweenD:'',
    }
  },

  methods: {

    yearInformation(){
       const date1 = new Date(this.picker1)
       const date2 = new Date(this.picker2) 
       let day1 = this.weekday[date1.getDay()]
       let day2 = this.weekday[date2.getDay()]
       

       if(this.leapYear(date1)){
         this.leapYear1Message =  date1.getFullYear() + ' is a leap year and is ' + day1 
       }
       else{this.leapYear1Message = date1.getFullYear() + ' is not a leap year and is ' + day1 }
       
       if(this.leapYear(date2)){
         this.leapYear2Message = date2.getFullYear() + ' is a leap year and is ' + day2 
       }
       else{this.leapYear2Message = date2.getFullYear() + ' is not a leap year and is ' + day2 }

       if (date2 > date1){
         this.beteweenD = 'The difference beteween this dates is: ' + Math.floor(date2-date1)/(1000*60*60*24)
       }
       else {this.beteweenD = 'The difference beteween this dates is: ' + Math.floor(date1-date2)/(1000*60*60*24)}
    },

   


    leapYear(date) {
      const year = date.getFullYear()
      // return (year%4 === 0 && year%100 !==0 || year%400 === 0)
      if (year%4 === 0 && year%100 !==0 || year%400 === 0){
        return true
        }
      else{ 
        return false
      }
     
    },

  }


}
</script>>
