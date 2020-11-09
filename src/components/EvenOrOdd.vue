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
                    <v-btn @click="checkPrime(number1) + checkPrime2() + oddEven()+ primeF(number1)" 
                    class="primary">Submit</v-btn>
                </v-col>
                <v-col cols='4'>
               
                <v-alert>{{message1 + '  ' + message2}}</v-alert>
                <v-alert>{{message3 + '  ' + message4}}</v-alert>
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
            message1:'',
            message2:'',
            message3:'',
            message4:'',
            pArray:[],
            
            
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

        Even(num){
            if(num%2 === 0)
                return true
            else
                return false
        }, 

    /*  primeF(factor){
            let x = 2;
            while(x <= factor )
                if (factor%x === 0){
                    factor = factor/2
                    pArray.push[x]
                    }
                elseif (prime(x) === true){
                        pArray.push[x]
                        x = factor
                        }
                    x = x + 1
        },*/

    

        checkPrime(num){
            
            for(let i = 2; i < num; i++ ){    
                if (num % i === 0)
                    
                  return this.message1 = num + ' is not Prime '    
            }
            return this.message1 = num + ' is a Prime'      
        },

        checkPrime2(){
            
            for(let i = 2; i < this.number2; i++ ){
                if (this.number2 % i === 0)
                   return this.message2 = this.number2 + ' is not Prime '    
            }
            return this.message2 = this.number2 + ' is a Prime'      
        },


        oddEven(){
            if(this.number1%2 === 0)
                this.message3 = this.number1 + ' is even'
                               
            else
                this.message3 = this.number1 + ' is odd'          
            if(this.number2%2 === 0)
                this.message4 = this.number2 + ' is even' 
            else
                this.message4 = this.number2 + ' is odd' 
        },
    }

}
</script>

<style>

</style>