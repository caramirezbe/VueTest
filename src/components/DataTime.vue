<!-- - Read a date (day month year). (Bonus: use <v-date-picker>)
    Show time between that day and today.
    Show day of the week (write your own function).
    Show is leap year (write your own function)
    (Bonus) Show if it's the first week of the month. -->

<template>
    <v-container>
        <v-toolbar flat color="blue">
            <v-toolbar-title>Time Problem</v-toolbar-title>
        </v-toolbar> 
            <v-row>
                <v-col cols=4>
                    <v-date-picker
                        v-model="date1"
                    ></v-date-picker>
                    <v-date-picker
                        v-model="date2"
                    ></v-date-picker>
                    <v-btn @click="dayPicker()" class="primary">Submit</v-btn>
                </v-col>
                <v-col cols=4>
                    {{this.message = date1}}
                    {{this.message = date2}}
                    {{year}}
                    
                </v-col>


            </v-row>



    </v-container>
    
    
</template>

<script>
export default {
    name: 'Datatime',

    data (){
        return {
            date1: new Date().toISOString().substr(0,10),
            date2: new Date().toISOString().substr(0,10),
        }   
    }, 

    methods:{
    
    dayPicker(){
        this.day= parseInt(this.date1)
        console.log(this.year)

    },


    },



}
</script>
