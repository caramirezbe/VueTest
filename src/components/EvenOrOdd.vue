<!--Excersice 1 
Read two integers:
    Show if they are even or odd listo
    Show if they are prime. listo
    Show all the prime factors. 
    Are they amigos (https://es.wikipedia.org/wiki/N%C3%BAmeros_amigos) suma de los primefactores es igual al otro
    Are they coprime  -->

<template>
  <v-container>
    <v-toolbar flat color="blue">
        <v-toolbar-title>Problems</v-toolbar-title>
    </v-toolbar>
        <v-form>
            <v-row>
                <v-col cols="4">
                    <v-text-field
                        v-model.number="number1"
                        label="Number 1"
                    ></v-text-field>
                    <v-text-field
                        v-model.number="number2"
                        label="Number 2"
                    ></v-text-field>
                    <v-btn @click="checkPrime() + checkPrime2() + oddEven() + printFactor() + sumPrimeF() + amicable() + coprime()" 
                    class="primary">Submit</v-btn>
                </v-col>
                <v-col cols='4'>
               
                <v-alert>{{ message1 + '  ' + message3 + message5}}</v-alert>
                <v-alert>{{ message2 + '  ' + message4 + message6}}</v-alert>
                <v-alert>{{ message7 }}</v-alert>
            </v-col>
            </v-row>
        </v-form>
  </v-container>
</template>

<script>
export default {
    name: 'EvenOrOdd',

    data (){
        return {
            number1:0,
            number2:0,
            array1:[],
            array2:[],
            message1:'',
            message2:'',
            message3:'',
            message4:'',
            message5:'',
            message6:'',
            message7:'',
            message8:'',
        }
    },

    methods:{

        prime(num){
            for(let i = 2; i < num; i++ ){
                if (num % i === 0)
                  return false    
            }
            return true  
        },

        even(num){
            if(num%2 === 0){
                return true
            }
            else{
                return false
            }
        }, 

        primeF(num){
            let i = 2
            const pArray = [] 
            while(i <= num){
                if(num%i === 0){
                    pArray.push(i)
                    num = num/i
                    }
                else{ 
                i++}        
           }
           return pArray
         },

        sumPrimeF(){
            const pArray = this.primeF(this.number1)
            let sum = 0
            for(let x=0; x<pArray.length; x++){
                sum = sum + pArray[x]
            }
            return sum
        },

        sumAmicable(num){
            const dArray = []
            let sum = 0
            for(let x = 0; x < num; x++){
                if(num%x ===0){
                    dArray.push(x)
                    sum += x
                }
            }
            return sum
        },

        coprime(){
            const small = this.number1 > this.number2 ? this.number1 : this.number2;
            console.log(small)
            for(let x = 2; x < small; x++){
                const a = this.number1%x === 0;
                const b = this.number2%x === 0;
                if(a && b){
                    this.message8 = ' no are coprimes '  
                }
            }
            this.message8 = ' are comprimes'

        },



        amicable(){
           if(this.sumAmicable(this.number1) === this.number2 && this.sumAmicable(this.number2) === this.number1){
                this.message7 = this.number1 + ' and ' + this.number2 + ' are amicable '
            }
            else { this.message7 = this.number1 + ' and ' + this.number2 + ' are not amicable ' }
        },


        checkPrime(){       
            if(this.prime(this.number1)){
                this.message1 = 'It is prime'
            }
            else {
                this.message1 = 'It is not prime'
            }      
        },

       checkPrime2(){       
            if(this.prime(this.number2)){
                this.message2 = ' is prime'
            }
            else {this.message2 = ' is not prime'
            }
        },

        oddEven(){
            if(this.even(this.number1)){
                this.message3 = ', is even'
                } 
            else{
                this.message3 = ', is odd'
                }
            if(this.even(this.number2)){
                this.message4 = ', is even' 
                }
            else{
                this.message4 = ', is odd' 
                }
        },

        printFactor(){
            this.message5 = ', is prime factors are ' + this.primeF(this.number1)
            this.message6 = ', is prime factors are ' + this.primeF(this.number2)
        },

    }
}
</script>

<style>

</style>